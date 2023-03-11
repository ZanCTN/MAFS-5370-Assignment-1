# MAFS-5370-Assignment-1
In this assignment we provide 4 approachs to the asset allocation problem:

-   Analytic Solution (AnalyticalSolution.ipynb)\
    In this approach we solve the Bellman Optimality Equation with the CARA Utility function $$U(W_{T})=\frac{1-e^{-\alpha W_{T}}}{\alpha}, \alpha\neq 0$$ and visualize the optimal asset allocation with different absolute risk averse parameter $\alpha = 0.001,0.01,...,100$

-   Textbook solution (TextbookAmmended.ipynb)\
    In this approach we tried to solve the problem with the help with the functions provided by the GitHub of Foundations of Reinforcement Learning with Financial Application. The textbook combines backward propagation with DNN. We change the distribution from Gaussian to Choose (specified by the provided package) and provide the function with a $pdf$. However the solution is sensitive to initial allocation i.e. it does not converge well even in $T = 1$

-   Tabular solution (Tabular_solution.ipynb)\
    In this approach, we discretized the state space $\mathcal{S}$ and action space $\mathcal{A}$ from continuous space into bins. We treated the state-action $q$ value function as a big $Q(s,a)$ table and perform tabular q-learning. The model converged well in smaller timestep setup (e.g. $T < 2$) and did not perform as well when $T$ increases to 10 steps, or it will take much larger number of episodes to explore the state-action spaces and update the tabular $Q$ function

-   Functional Approximation\
    We attempted to use Semi-Gradient SARSA algorithm in the Reinforcement Learning: An Introduction to approximate $Q$ function. For each functional form, both same $Q$ function for all time steps (SARSA.ipynb); and different $Q_t$ function for different time steps (SARSA_TimeDept.ipynb) (the functional approximation does not require the input of parameter $t$) is tested. We first test the functional form implied from the analytic solution, then testing some other possible forms. Although the parameters of the functional approximation converges in most of the case, the optimal allocation is very different from the analytic solution.\
    One possibility is "if the action space $\mathcal{A}$ is continuous, the learned value function $Q$ could have many local maxima and saddle points; therefore, naive approaches such as gradient ascent can be expensive and inaccurate" suggested in "Deep Radial-Basis Value Functions for Continuous Control": <https://arxiv.org/abs/2002.01883>

For detailed description of the four approaches, refer to the comments in the coding blocks and markdown cells in the 4 .ipynb files.

Remarks: the rl file and TextbookNormal.ipynb are ammended based on the GitHub for the Book Foundations of Reinforcement Learning with Financial Application: https://github.com/ShangtongZhang/reinforcement-learning-an-introduction for testing.
