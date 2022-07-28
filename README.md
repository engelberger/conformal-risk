# Conformal Risk Control
This is the official repository of <i>Conformal Risk Control</i> by Anastasios N. Angelopoulos, Stephen Bates, Adam Fisch, Lihua Lei, and Tal Schuster.

In the risk control problem, we are given some loss function $L_i(\lambda) = \ell(X_i,Y_i,\lambda)$.
For example, in multi-label classification, you can think of the loss function as the false negative proportion $L_i(\lambda) = 1 - \frac{|Y_{i} \cap \mathcal{C}_{\lambda}(X_{i})|}{ |Y_i|}$, where $\mathcal{C}_{\lambda}(X_{i})$ is the set-valued output of a machine learning model. 
As $\lambda$ grows, so does the set $\mathcal{C}_{\lambda}(X_{i})$, which shrinks the false negative proportion.
On a <i>new test point</i>, we seek to control the expected value of its loss, $$\mathbb{E}\big[L_{n+1}(\hat{\lambda})\big]$$, where $\hat{\lambda}$ was chosen based on the first $n$ data points.
