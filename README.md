# COL778 - Principles of Autonomous System
This repository ccontains assignments, lecture notes, books and other resources for the course [COL778](https://lily-molybdenum-65d.notion.site/COL778-Principles-of-Autonomous-Systems-eb895fb5ac0d4edc860533439cce8fa7)/[864](https://lily-molybdenum-65d.notion.site/COL864-Special-Topics-in-AI-Embodied-AI-28e0e65bfef34ee8a9905375f5e419b3) offered by [Prof. Rohan Paul](https://www.cse.iitd.ac.in/~rohanpaul/index.html) in the semester 2302 at IITD. The [course](https://lily-molybdenum-65d.notion.site/COL778-Principles-of-Autonomous-Systems-eb895fb5ac0d4edc860533439cce8fa7) deals with the algorithmic aspects of intelligent robotics and more generally autonomous systems. 
## Topic wise resources
1) State Representation
   - Read about homogenous transforms [here](https://mecharithm.com/learning/lesson/homogenous-transformation-matrices-configurations-in-robotics-12#).
2) State Estimation using Kalman Filters
   - Read about Conditioned Joint Gaussian PDFs [here](https://bmeyers.github.io/conditional_distribution_for_jointly_gaussian_random_vectors/).
   - Calculation of co-variance matrix $\sum_{X_tX_{t+1}}$ used in derivation of the action update equations:
     
     $\sum_{X_{t+1}X_t}$ = $\mathbb{E}[(X_{t+1} - \mu_{X_{t+1}})(X_t - \mu_{X_t})^T]$

     $\sum_{X_{t+1}X_t}$ = $\mathbb{E}[(X_{t+1} - A_t\mu_t - B_t\mu_t)(X_t - \mu_t)^T]$

     $\sum_{X_{t+1}X_t}$ = $\mathbb{E}[(A_tX_t - A_t\mu_t + \epsilon_t)(X_t - \mu_t)^T]$

     $\sum_{X_{t+1}X_t}$ = $\mathbb{E}[(A_tX_t - A_t\mu_t + \epsilon_t)(X_t^T - \mu_t^T)]$

     $\sum_{X_{t+1}X_t}$ = $\mathbb{E}[A_tX_tX_t^T - A_t\mu_tX_t^T + \epsilon_tX_t - A_tX_t\mu_t^T + A_t\mu_t\mu_t^T - \epsilon_t\mu_t^T]$

     Since $\epsilon_t$ is an independent zero-mean random variable, all terms with $\epsilon_t$ go to 0

     $\sum_{X_{t+1}X_t}$ = $\mathbb{E}[A_tX_tX_t^T - 2 * A_t\mu_tX_t^T + A_t\mu_t\mu_t^T]$

     $\sum_{X_{t+1}X_t}$ = $A_t\mathbb{E}[X_tX_t^T] - A_t\mu_t\mu_t^T$

     $\sum_{X_{t+1}X_t}$ = $A_t(\mathbb{E}[X_tX_t^T] - \mathbb{E}[X_t]\mathbb{E}[X_t]^T)$

     $\sum_{X_{t+1}X_t}$ = $A_t\sum_{t|0:t}$


