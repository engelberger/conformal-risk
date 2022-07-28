# Conformal Risk Control
This is the official repository of <i>Conformal Risk Control</i> by Anastasios N. Angelopoulos, Stephen Bates, Adam Fisch, Lihua Lei, and Tal Schuster.

## Technical background
In the risk control problem, we are given some loss function $L_i(\lambda) = \ell(X_i,Y_i,\lambda)$.
For example, in multi-label classification, you can think of the loss function as the false negative proportion $L_i(\lambda) = 1 - \frac{|Y_{i} \cap C_{\lambda}(X_{i})|}{|Y_i|}$, where $C_{\lambda}(X_{i})$ is the set-valued output of a machine learning model. 
As $\lambda$ grows, so does the set $C_{\lambda}(X_{i})$, which shrinks the false negative proportion.
We seek to choose $\hat{\lambda}$ based on the first $n$ data points to control the expected value of its loss <i>on a new test point</i> at some user-specified risk level $\alpha$, $$\mathbb{E}\big[L_{n+1}(\hat{\lambda})\big] \leq \alpha.$$

## Examples
Each of the `{polyps, coco, hierarchical-imagenet, qa}` folders contains a worked example of conformal risk control with a different risk function.
`polyps` does gut polyp segmentation with false negative rate control. `coco` does multi-label classification with false negative rate control. `hierarchical-imagenet` does hierarchical classification and chooses the resolution of its prediction by bounding the graph distance to an ancestor of the true label. Finally, `qa` controls the F1-score in open-world question answering.

The core algorithm is in `core/get_lhat.py`. It is 5 lines long.
