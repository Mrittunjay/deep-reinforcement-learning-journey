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
It is a value based Reinforcement Learning Algorithm. It tries to learn the quality(Q-value) of each action in each state. The Q-value represents how good it is to take a particular action on a given state. The agent uses these Q-values to choose the best possible action. In the Q-table, the action values are learned and updated iteratively through agent's interection with the environment. 

        Q-Values are updated using the Bellmen Equation:
        Q(s,a) = Q(s,a) + (alpha)[r + (gamma)maxQ(s',a') - Q(s,a)] 
        
        Where:
        s: current state
        a: action taken
        r: reward received
        s': next state
        alpha: learning rate
        gamma: discount factor (how much future rewards are valued)

Deep Q-Network(DQN):
----------------
In environments like cartpole, the number of states are continewous(not finite), so we cannot store Q-values in a table, instead we use a neural netwrok to approximate the Q-function this is called a Deep-Q-Network.

DQN Workflow:
--------------
1. Observe the current state(cart position, pole angle, etc).
2. Predict Q-value for each possible action(move left or move right).
3. Choose an action.
   
        a. Either random (Exploration).
        b. Or one with highest predicted Q-value (Exploration).

5. Perform the action and get next state and reward.
6. Store (state, action, reward, next state) tuple in a reply buffer.
7. Train the network using random sample from the buffer.
8. Update the target network periodically for stability.
9. The agent uses an ε-greedy strategy:

        a. With probability ε, choose a random action (explore)
        b. With probability 1−ε, choose the best-known action (exploit)
        c. At the start, ε is high (e.g., 1.0) → agent explores more.
           Over time, ε decays to a small value (e.g., 0.02) → agent exploits what it has learned.
    
10. Learning process

        a. The reward per episode starts low(pole falls quickly)
        b. Gradually, as the Q-Network improves, the agent balances the pole longer.
        c. A well trained agent can keep the pole upright for more than 450 steps, and in my case parfect score is 500 steps. 


Note: A good introduction to reinforcement learning
https://www.youtube.com/watch?v=VnpRp7ZglfA&t=3372s

Note: The following links have some decent explanation about Q-Learning in CartPole project. My code is not inspired from the following given links. Just porvided the links for sharing knowlege purpose. 
https://aleksandarhaber.com/q-learning-in-python-with-tests-in-cart-pole-openai-gym-environment-reinforcement-learning-tutorial/
https://www.youtube.com/watch?v=KMjQmG5Uzis


