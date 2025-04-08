#### What is simulation?
- the "dataset" for RL is the simulation

#### Why do we need simulations?
- most tasks have many ways that you can do them
	- "do my laundry" has many paths to various degrees of success
- the agent does not usually know the "global" optimal solution ahead of time
	- need to explore
	- finding many solutions let you figure out what is good and what is not
- exploration in the real world is very expensive
	- imagine training a robot in the real world to do your laundry
		- incurring many running costs
		- robots are also fragile
	- the ways that the robot explores might not be safe
		- putting the clothes in the dryer before the washer
		- doing something to cause the machines to short circuit
	- starting an agent from scratch $\rightarrow$ they will be making mistakes
		- if you do this in the real world, there are real world consequences as opposed to doing this in a simulation
- even with very simple rules, you are able to observe complex behaviors

#### Basic components of a simulation
- from a MDP perspective
	- contains at least S, A, and T
		- S = set of all states in the world
			- in the Conway example, the snapshot of the entire world at each time step is a state
		- A = set of all actions
			- what are the things that are available for the agent to do
		- T  = transition matrix
			- the agent takes in some state and performs some action
				- the environment operates according to this transition matrix
				- state x action --> new state
- there are pre-conditions that need to be met to perform a certain action, and post-conditions that are true after
	- just a different framing to things we learn in software
- technically, an explicit reward is not necessary
	- don't need to have a goal
	- implicit motivation

#### Sim2real transfer
- does an agent trained in simulation transfer to reality
	- same question as "does your model extrapolate out of distribution"
- answer: not really (for now)
	- the rule of thumb is to make the sim as close to reality as you can

#### Cognitive complexity
- requires long chains of reasoning
- think puzzles, math problems, moral dilemmas, etc.
	- a lot of cognitive benchmarks are done against real people

#### Perceptive complexity
- how are you interacting with the world?
- perception refers to things like high levels of vision and/or precise motor skills
	- requires high levels of these things
- ex.
	- bird watching, threading a needle, Where's Waldo

#### Matrix of simulations
- x-axis: cognitive
- y-axis perceptive
	- reality is somewhere in the far, upper-right corner of the first quadrant

#### Low perceptive, low cognitive
- gridworld
	- great for understanding the basics of RL and dynamic programming
- imagine every single grid is an entire state
- interesting tweaks
	- uncertainty can be added for each of the actions taken

#### Low perceptive, medium cognitive
- Atari
	- the first time that we were able to make agents that could beat humans in atari games
	- games like Pong, Brick-breaker
	- relatively simple action spaces
		- decent bit more complex than gridworld

#### Low perceptive, high cognitive
- Zork, NetHack
	- pretty complex videogame that does not really have graphics
	- AI struggles with these because they are hard cognitive tasks
- why is this such a hard task?
	- is it a memory thing?
	- processing power?

#### Medium perceptive, low cognitive
- an image is presented
	- are there an equal number of large things and metal spheres?

#### Medium perceptive, medium cognitive
- Ai2 THOR
	- egocentric perspective of a robot
		- pick and place
	- not too complicated, but more complicated for sure than the other tasks
	- the important thing here is that it requires being able to perceive and interact with the world
- AppWorld (Trivedi et al. 2024, ACL)
	- less embodied setting
	- on AI agents
		- figuring out with getting these agents to interact with apps
	- training on a virtual environment
	- building up to a personal assistant
		- "buy me x from Amazon"
		- "play me song y from Spotify"
		- "answer my email for me"

#### Medium perceptive, high cognitive
- Minecraft
	- you can build effectively anything in the world
	- has internal languages, scripting languages that are Turing complete
- medium perceptive because the whole world is still discretized

#### High perceptive, low cognitive
- basically all the robot sims
- Mujoco
- the world is simulated
	- there is physics included
		- gravity
		- friction
		- servos
		- joints
	- figuring out a policy for a robot to stand up and to move around
		- simple from a cognitive perspective
	- high fidelity simulation from the perception perspective
- Habitat
	- (Meta, Savva et al. 2019)
	- trying to have high perception without losing out on the cognitive task
		- e.g. go take my laundry basket from the laundry room to the bedroom

#### High perceptive, high cognitive
- real world, whoever gets this sim first cheaply wins
	- there does not exist a simulation that does this
	- basically winning the getting to AGI competition

#### Questions to think about
- when I am picking a task/environment to do a project on
	- for all the sims, how were the dimensions of complexity related to the size of the state/action space
	- how were they related to how many steps you'd have to take before getting a reward?
		- (aka reward sparsity)

#### Sim2real Transfer
- which dimensions of complexity transfer more easily to reality?
- can you train on lower complexity and switch to a higher complexity?
- (world model holy grail) sims are very costly to make, can you just learn one?