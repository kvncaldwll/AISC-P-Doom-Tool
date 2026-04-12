**AI existential risk probability tree**

an interactive tool for mapping probabilites for AI-caused doom
built as part of [AISC - Project 19](url)


**Framing**

this is an environment-first approach to AI risk
"dangerous" is a property of the configuration between optimization and environment, not just the agent capability
instead of "what properties must AI have to be dangerous":
- can AI optimization worsen dangerous conditions in the environment?
- does that worsening outpace corrective capacity?

this is agnostic of:
- intent (malicious, accidental, misuse)
- system architecture (single agent, multipolar, emergent dynamics)
- specific AI capabilities (intelligence, strategic planning, etc)

**Notation**

E = environment (internally coupled such that changes propagate to K)
K = dangerous conditions (subset of E)
K₀ = current state of K at time t
K+ = K worsening
t = point in time at which K and R₀ are sampled
R₀ = rate of change of K at t (baseline, current trajectory)
Rc = rate at which corrective capacity can negate K+
O = optimization (preference ordering of actions to achieve desired outcome)
M = K is mutable (accessible, changeable)
C = O sufficient to change E

DAI = AI where K+ | O > R₀
AI optimization accelerates dangerous conditions worsening beyond current trajectory

Lock in = K+ > Rc
worsening outpaces corrective capacity

Doom = DAI ∧ Lock in
AI accelerates worsening AND corrective capacity can't keep up

**Tree**

Doom [AND] — D = DAI ∧ Lock in
├── AI increases P(Doom) [AND] — DAI = K+ | O > R₀
│   ├── K is mutable [LEAF] — M
│   └── O sufficient to mutate K [LEAF] — C
└── Lock in [LEAF] — K+ > Rc

P(Doom) = P(M) × P(C) × P(Lock in)

**usage**

the tool lets you:
- select a risk vector (autonomous misaligned, human misuse, emergent dynamics)
- select a substrate (human life, sustaining environment, infrastructure/civilization)
- set a time window (10, 30, 100 years)
- adjust confidence sliders for each leaf node
- see how P(Doom) changes based on your assumptions

sliders represent _confidence_ that a condition holds (1-99%), not the degree to which it holds.

**key considerations**

we can't empirically isolate AI's contribution to the rate of change from other pressures (climate, geopolitics, etc)
the tool is designed for users to assign their confidence to how much they think AI contributes, ideally grounded in evidence
the baseline R₀ at time t already includes existing AI effects making the comparison against the current trajectory, not a hypothetical world without AI
