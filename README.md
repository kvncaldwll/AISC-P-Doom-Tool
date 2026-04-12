# Doom Assumptions

an interactive tool for mapping assumptions about AI-caused doom, built as part of [AISC Project 19](https://www.aisafety.camp/#h.pxd3zndm22u4)

## framing

this tool takes an environment-first approach to AI risk — danger is a property of the configuration between optimization and environment, not just agent capability alone

instead of asking "what properties must AI have to be dangerous?"
- can AI optimization worsen dangerous conditions in the environment?
- does that worsening outpace corrective capacity?

this is agnostic of
- intent (misaligned, misused, accidental)
- system architecture (single agent, multipolar, emergent dynamics)
- specific capabilities — as long as it can change the environment, it's capable

## notation

| Symbol | Meaning |
|--------|---------|
| E | Environment (internally coupled such that changes propagate to K) |
| K | Dangerous conditions (subset of E) |
| K₀ | Current state of K at time t |
| K+ | K worsening |
| t | Point in time at which K and R₀ are sampled |
| R₀ | Rate of change of K at t (current trajectory) |
| Rc | Rate at which corrective capacity can negate K+ |
| O | Optimization (preference ordering of actions to change E) |
| M | K is mutable (accessible, changeable) |
| C | O sufficient to mutate K (directly or through E) |

**DAI** = AI where K+ | O > R₀  
AI optimization accelerates dangerous conditions worsening beyond current trajectory

**Lock in** = K+ > Rc  
worsening outpaces corrective capacity

**Doom** = DAI ∧ Lock in  
AI accelerates worsening AND corrective capacity can't keep up

## tree

```
Doom [AND] — D = DAI ∧ Lock in
├── AI increases P(Doom) [AND] — DAI = K+ | O > R₀
│   ├── Dangerous conditions are changeable [LEAF] — M
│   └── Optimization sufficient to change them [LEAF] — C
└── Lock in [LEAF] — K+ > Rc
```

P(Doom) = P(M) × P(C) × P(Lock in)

## usage guide

**single scenario tab**
- pick a risk vector and substrate
- set a baseline snapshot and a future projection
- adjust confidence sliders for each node
- see P(Doom) trajectory

**all trajectories tab**
- view all 9 configurations (3 risk vectors × 3 substrates) simultaneously
- a 3×3 matrix shows P(Doom) at baseline and projection for every combination
- click any cell to open a side panel and adjust its sliders
- an envelope chart shows the collective trajectory as a band spanning worst to best case, with a median line through the middle

### risk vectors
- misaligned — autonomous AI whose optimization is misaligned with human interests
- misuse — human-directed AI used to cause harm
- emergent — aggregate effects of widely deployed AI systems

### substrates
- human life
- sustaining environment
- infrastructure / civilization

### reading the envelope

the band represents the range of P(Doom) across all 9 configurations at each point in time. band height shows how bad things are. Band width shows how much your assumptions matter. Widening over time means scenarios are diverging — narrowing means they're converging.

## baseline

at any snapshot in time t, dangerous conditions K have a current state (K₀) and rate of change (R₀). R₀ already includes all existing pressures — climate, nuclear risk, existing AI effects, everything. the question is whether additional AI optimization makes the rate worse from here.

## key considerations

- **Attribution:** we can't empirically isolate AI's contribution to the rate of change from other pressures (climate, geopolitics, etc). the tool is designed for users to assign their confidence to how much they think AI contributes, ideally grounded in evidence.

## author

kevin caldwell — [AISC Project 19](https://www.aisafety.camp/#h.pxd3zndm22u4)

## license

MIT
