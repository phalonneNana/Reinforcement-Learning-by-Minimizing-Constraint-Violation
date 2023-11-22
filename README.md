# Goal
This research proposes the integration of violation measures in reinforcement learning to enhance the
decision-making capabilities of intelligent agents in complex environment that requires safety. Two main
approaches are investigated: one involving the incorporation of violation penalization within the reward
function and another with external violation measures. We explore a basic environment with single and
multiple constraints, as well as a larger environment with three distinct constraints. Notably, varying
parameter configurations and threshold values are used to evaluate the impact on agent performance,
which is trained using Q-learning algorithm, and, in addition, a similar value that we call U-values
are learned to quantify constraint violations with the goal of minimizing it. 


# Environment
hey comprise several
essential elements, including states, actions, reward function, and an exploration-exploitation strategy.
These elements are fundamental to understanding the behavior of agent within this environment. 
I will define the basic environment that serves as the stage for agents with the aim of achieving 
an equilibrium: to maximize reward by collecting valuable resources, referred to as ”sweets,” in 
selected states (those without mud), while diligently avoiding states with predefined constraints. It consists of :

###  States :
States represent the different situations or configurations that the agent can encounter
while interacting with the environment. In our case, states are characterized by specific attributes,
which include:
- Battery Levels: These can be categorized as either ’Low’ or ’High.’ They indicate the energy
level of the agent’s power source.
- Wind Conditions: Wind conditions are classified as ’Calm’ or ’Windy,’ reflecting the weather
conditions in the environment.
- Mud Conditions: Mud conditions can be ’Yes’ or ’No,’ signifying the presence or absence of
Mud.
- X and Y Coordinates: These represent the agent’s positional coordinates within the environment,
ranging from 1 to 5.
To systematically explore and represent all possible scenarios in our environment, we create a
comprehensive list known as the ”state space.” This list contains every conceivable state within
our environment. We construct this list by exhaustively combining all the attribute values, ensuring
that no potential state is overlooked.

###  Actions : 
The agent within the environment has a set of actions it can take to interact with its
surroundings. These actions include: Move Up, Move Down, Move Right, Move Left, Stay (The
agent remains stationary). These actions form the basis for the agent’s decision-making process
and influence its interactions with the environment.

### Reward Function : 
In our implementation, it plays a pivotal role, where rewards are carefully
allocated to guide the agent’s actions and outcomes.
- The agent receives a substantial positive reward (10.0) for achieving a ”final state.” A final state
is defined by specific conditions, such as the absence of Mud, the agent’s position at coordinates (5,
5), a high battery level, and calm wind conditions. This high reward acknowledges the successful
completion of the agent’s primary objective.
- In states without Mud, where the agent can collect valuable resources termed ”sweets,” a
smaller positive reward (1.0) is awarded. This encourages the agent to seek out and collect these
resources, in line with its first objective.
- In all other scenarios, where neither a final state nor the collection of sweets is achieved, a
negative reward (-1.0) is issued. This discourages the agent from taking actions that do not
contribute to its goals and encourages a maximization of reward.

### ε−greedy strategy : 
the second goal of the agent being to minimise the violation of the constraint,
it thus aim to maximize rewards while maintaining safety and adhering to constraints. This delicate
equilibrium forms the core of the exploration-exploitation strategy, a critical component in our
environment’s decision-making process.
- Exploration: The exploration aspect of this strategy recognises the uncertainty inherent in
the environment. When guided by a probability defined by ε, the agent takes a bold step into
unknown territory. To do this, it selects actions at random from the set of available actions. This
adventurous approach allows the agent to accumulate new experiences, which can lead the agent
to discover previously ignored ’sweets’ or to reveal alternative routes that mitigate safety risks.
- Exploitation: On the other hand, exploitation represents a more conservative approach. When,
with a probability of 1 − ε, the agent opts for exploitation, he deliberately chooses actions that are
known to have produced promising results in the past. This choice is not arbitrary; it is based on a
careful evaluation of the historical performance of each action. Here, the agent focuses on actions
that have been shown to be effective in achieving specific goals, such as collecting sweets in Mud-
free states while avoiding constraints states. These actions are guided by Q-values, which reflect
the estimated value of each action based on previous experience. In addition, U-values provide
a broader perspective by taking into account the minimization of violation of those constraints.
Exploitation, in our environment, is aligned with the agent’s primary goal and capitalises on known
strategies to maximise rewards and minimise constraint violation.
This strategic balance between exploration and exploitation is of most important on ensuring
that the agent navigates its complex environment optimally. Exploration allows the agent to
adapt to change and discover new opportunities, while exploitation allows it to capitalise on
established practices. Importantly, this strategy integrates the complex nature of the trade-off
between maximizing rewards and ensuring safety. In an environment that constantly changes,
the agent must judiciously balance the benefits of both exploration and exploitation to effectively
pursue its dual objective: gathering sweets and ensuring safety

# Result
Our findings suggest that incorporating violation penalization within the reward function leads to more 
stable and robust results, indicating the significance of the choice of approach in handling constraints. 
In complex environments with multiple constraints, agent performance exhibites fluctuations, showing the 
importance of adaptive threshold values.

### I did 3 implementations and the notebook you will find is just for one implementation. Go through and contact me for more detail.

# GOOD READING😁😁😁
