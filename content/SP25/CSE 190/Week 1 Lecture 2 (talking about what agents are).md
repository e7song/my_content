#### Brief history of agents
- simulations $\rightarrow$ to the real world
- a lot of it is built on dynamic programming and neuroscience
	- modeling the brain as a MDP, rewards being things like hormones, etc.

#### Sequential decision making
- the difference from ML problems like classification is that you are doing things in a long sequence
	- a sequence of decisions rather than a single decision
	- e.g. laundry robot steps
		- even if at each step you were able to pick the right move at a 99% accuracy, by the time you reached 120 steps the accuracy is ~30%
- we are optimizing across a long sequence of issues

#### Markov decision process
- core problem formulation for what RL looks like
- general speaking, there is an agent (robot, etc.)
	- at a discretized time step (generally), the robot performs an action
		- picking up a remote, finding a detergent, etc.
	- agent executes the action in an environment--the rest of the world not including the agent (more on this later)
	- environment changes because of this action; generates a new state $S_{t+1}$
	- environment can also generate a reward $R_{t+1}$ to give feedback on if the task is actually being completed or not
	- these environmental outputs are fed back into the agent

#### MDP (modern LLM version)
- shopping agent; it's purpose is to help you find fashion
	- instruction is the state
	- performs search $[\text{contents}]$
	- performs click
	- after seeing the state, backtracking to search more specifically
	- click buy
- bonus: what does a MDP for language generation look like?
	- what does it meant o generate language and frame it as a reinforcement learning problem

#### Components of an agent
- might have different definitions per whoever does the research
- ref slide

#### Grounding (in an environment)
- language is anchored to concepts in the world
	- does "weight" have a meaning if it is not tied to the physical sense
- many types of language grounding
	- to other modalities--images, phrases
		- image is worth a thousand words
	- to social / cultural norms
	- to action
		- pick up the cup from the right side of the table
		- actually anchored to a particular action being done in the world

#### Agency
- agents require agency
	- choices are required for actions
- if an agent has to select what tools to use but there is always only one tool, is that agency?
	- it's more workflow automation at this point
	- the agent needs to have the ability to select its tools

#### Agent vs. environment
- no good definition (unless  you count religious philosophy)
	- some definitions that make the math easier
- some rules of thumb
	- there are some situations from this relationship where the line between the agent and the environment is blurred
	- strictly define the task
		- make these definitions from the perspective of the task you want to do
	- think about which one is easier to modify the behaviors of

#### Memory
- agents can know what they just performed and it can influence what they will do next
- short term
	- what is the relevant information around me that I can need to use to act *now*
- long term
	- what information have I already learned can be used to help me now

#### (Long horizon) planning / reasoning
- 1 step 99% accuracy over even 120 steps = <30%
- agent is trying to optimize across the entire sequence rather than at a single step (as opposed to traditional ML)

#### Learning (from feedback)
- the ability to learn is very important
- many different types of feedback
	- get feedback on if the task was completed; use this to update the priors
- independent of "learning" mechanism
- doesn't necessarily need to update model weights
	- in context learning (model responding to a prompt "no you got that wrong" is also learning from feedback)

#### (additional components) $\downarrow$

#### Embodiments
- robots
- physically acting in the real world
- "embodied" hypothesis that says embodiment is necessary for true general intelligence (AGI)


#### Communication
- can the agent communicate its intentions to other agents
- a necessary pre-req for multi-agent scenarios
	- what is a multi-agent scenario?
		- making sure two agents aren't doing the same work
		- making them communicate their competencies

#### World modeling
- mathematical definition
	- modeling the transition matrix $T$ by MDP
		- environment takes in action and changes; the transition matrix represents this change
		- input is the environment and the action; the output would be the next state
- given the state of the world and an action, predict the next state of the world
	- trying to learn this transition function

#### Multimodality
- the initial jump in LLM advancement has been boosted by scraping the internet and cleaning this information up
	- however, we only have one internet and it only gets so much better each year
		- makes it hard for the current generation to keep scaling up
	- there are currently only a few trillion tokens of "clean" text ~= a few terabytes
		- clear limit on scaling
		- current internet took us ~2-3 decades to generate this much data
- however, there is a lot of data in other sources
	- YouTube has 4.3 petabytes of new videos a day
	- CERN generates 1 petabyte of data a day (of the physical world)
- modalities exist outside of vision and language
	- efficient use of this data is critical to scaling further

#### Components of an agent
- required
	- grounding, agency, planning, memory, learning
- additional
	- embodiment, communication, world modeling, multimodality
- why are some required and why are some additional?
	- the strictest, smallest definition of models are things that act within some environment
	- the additional components are more implementation techniques for how you would get more realistic agents

#### Model vs AI system vs agent: rough intuition
- model
	- GPT-4
	- literally the weights of the model online
	- forward passes of neural net
- AI system
	- ChatGPT
		- mixing models together
		- model + scaffolding, but no agency
- Agent
	- ChatGPT (computer use)
	- "take over my computer and do a task"
		- I have a task and I describe it in a natural language; want the agent to perform the task for me
	- has agency + discussed components

#### Agent or not?
- some examples
	- auto pilot
		- yes
			- need to have some amount of context for what is happening around you
			- decisions are being made based on the environment
	- automated JavaScript buttons
		- no
			- generally not really considered agents
	- retrieval augmented generation
		- no
			- document is retrieved from the internet, questions answered based on it
			- like the automated JavaScript buttons, there is a bunch of predefined steps
				- there is no agency
	- warehouse robots
		- yes
			- can be agents depending on how much autonomy they have
	- gameplay agents
		- yes
			- RL agents from Dota or League of Legends
	- (current) house robots
		- unclear
			- lack some components, but this won't be the case forever
	- voice assistants (early Alexa / Siri)
		- no
	- voice assistants (Gemini, GPT + Apple)
		- clearly moving towards having some agentic behavior
		- a lot of these voice assistants are not there right now
			- promising signs; can chain things together
				- write me some text in a google doc and then send this email out that has this google doc attached

#### It is ok to not use an agent!
- not every use case needs an agent
	- most use cases just need models or "AI systems"
- agents are complicated
	- if you don't need one, then don't use it
	- first try the simplest method you have for your task