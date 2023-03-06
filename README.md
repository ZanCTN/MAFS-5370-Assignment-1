# MAFS-5370-Assignment-1
In this assignment we provide 4 approachs to the asset allocation problem:

-   Analytic Solution\
    In this approach we solve the Bellman Optimality Equation with the CARA Utility function $U(W_{T})=\frac{1-e^{-\alpha W_{T}}}{\alpha}, \alpha\neq 0$ and visualize the optimal asset allocation with different absolute risk averse parameter $\alpha = 0.001,0.01,...,100$

-   Tabular solution

-   Functional Approximation\
    We attempted to use Semi-Gradient SARSA algorithm in the Reinforcement Learning: An Introduction to approximate Q function. For each functional form, both same Q function for all time steps; and different Q function for different time steps (the functional approximation does not require the input of parameter t) is tested. Although the parameters of the functional approximation converges in most of the case, the optimal allocation is very different from the analytic solution.\
    One possibility is "if the action space A is continuous, the learned value function Q could have many local maxima and saddle points; therefore, naive approaches such as gradient ascent can be expensive and inaccurate" suggested in "Deep Radial-Basis Value Functions for Continuous Control" <https://arxiv.org/abs/2002.01883>

For detailed description of the four approaches, refer to the comments in the coding blocks and markdown cells in the 4 .ipynb files.
