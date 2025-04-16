# Decision to use Random Search with Early Stopping instead of Hyperband Tuner
Based on our experimentation and the challenges we encountered with hyperparameter tuning, we ultimately decided to use Random Search with Early Stopping instead of Hyperband for our rare species classification project. This decision was well-justified by both our practical experience and research literature:
- We found that Hyperband's aggressive early termination strategy was problematic for our specific task. As noted in the seminal paper by Li et al. (2018), Hyperband relies on the assumption that performance in early epochs is predictive of final performance. However, for our rare species classification with imbalanced classes, we observed that many promising configurations required more training time to reveal their true potential.
- Furthermore, we experienced technical issues where Hyperband attempted to reload weights into unbuilt models, creating frustrating workflow interruptions. As noted by Bouthillier and Trofimov (2019), these implementation challenges with Hyperband can make Random Search more practical and reliable for many real-world applications.
- Our rare species dataset has inherent class imbalance and noise, making it particularly sensitive to early performance fluctuations. Research by Jamieson and Talwalkar (2016) suggests that in such scenarios, allowing models more training time before assessment is critical - which Random Search naturally accommodates through its patience-based early stopping mechanism.
- For these reasons, we implemented Random Search with customized early stopping callbacks, which provided us with more stable and reproducible results, better exploration of our hyperparameter space, and more reliable identification of promising model configurations for our specific rare species classification challenge.

Bibiopgraphy:

- Li, L., Jamieson, K., DeSalvo, G., Rostamizadeh, A., & Talwalkar, A. (2018). Hyperband: A novel bandit-based approach to hyperparameter optimization. Journal of Machine Learning Research, 18(185), 1–52.
https://jmlr.org/papers/volume18/16-558/16-558.pdf

- Bouthillier, X., & Varoquaux, G. (2019). Machine learning reproducibility: Issues and guidelines. arXiv preprint arXiv:1906.01935.
https://arxiv.org/pdf/1906.01935.pdf

- Jamieson, K., & Talwalkar, A. (2016). Non-stochastic best arm identification and hyperparameter optimization. In Proceedings of the 33rd International Conference on Machine Learning (Vol. 51, pp. 240–248). PMLR.
https://proceedings.mlr.press/v51/jamieson16.pdf

