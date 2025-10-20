CartPole-v1 (Deep Q-Learning)
------------------------------
The cartpole project teaches an agent how to balance a pole on a moving cart by rewarding stability and pelalizing failure, using traial and error and neural network based Q-Value estimation. Over thousands of episode the agent learns which moves keeps the pole upright, demonstrating the power of Reinforcement Learing

CartPole-v1 environment:
-------------------------
1. A pole is balanced on a moving cart.
2. The agent can move the cart left or right.
3. The episode ends if the pole falls too far or the cart moves out of bound.

Q-Learning concept:
--------------------
It is a value based Reinforcement Learning Algorithm. It tries to learn the quality(Q-value) of each action in each state. The Q-value represents how good it is to take a particular action on a given state. The agent uses these Q-values to choose the best possible action. 
Q-Values are updated using the Bellmen Equation:
        Q(s,a) = Q(s,a) + (alpha)[r + (gamma)maxQ(s',a') - Q(s,a)] 
        
Where:
1. s: current state
2. a: action taken
3. r: reward received
4. s': next state
5. alpha: learning rate
6. gamma: discount factor (how much future rewards are valued)

Deep Q-Network:
----------------
In environments like cartpole, the number of states are continewous(not finite), so we cannot store Q-values in a table, instead we use a neural netwrok to approximate the Q-function this is called a Deep-Q-Network.


dfdfd


Note: A good introduction to reinforcement learning
https://www.youtube.com/watch?v=VnpRp7ZglfA&t=3372s

Note: The following links have some decent explanation about Q-Learning in CartPole project. My code is not inspired from the following given links. Just porvided the links for sharing knowlege purpose. 
https://aleksandarhaber.com/q-learning-in-python-with-tests-in-cart-pole-openai-gym-environment-reinforcement-learning-tutorial/
https://www.youtube.com/watch?v=KMjQmG5Uzis


