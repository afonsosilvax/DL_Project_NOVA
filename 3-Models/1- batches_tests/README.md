Based on the model performance curves we've analyzed, we decided that a batch size of 64 is the most appropriate choice for our rare species classification project for several compelling reasons:
- In our experiment, we found that a batch size of 64 strikes an optimal balance between memory efficiency and computational performance. This is particularly important when working with the high-resolution images (224×224) that we need for accurate rare species identification.
- Looking at our training curves, especially in the batch of 64, we observed stable convergence patterns. The loss curves demonstrate consistent downward trends without severe oscillations, suggesting that this batch size provides sufficient statistical estimation of the gradient.
- The validation accuracy curves show reasonable generalization, with a manageable gap between training and validation performance. This indicates to us that batch size 64 provides a good balance between noisy updates (from too small batches) and overly deterministic updates (from too large batches).
- Our decision is also supported by established research in the field. Keskar et al. (2017) demonstrated that moderate batch sizes like 64 often lead to better generalization than very large batches. Masters and Luschi (2018) specifically found that batch sizes in this range strike an excellent balance between training efficiency and generalization capability.
For our rare species dataset with inherent class imbalance, this batch size helps ensure that even less common classes have a reasonable probability of appearing in each training batch.

Bibiography:
- Keskar, N. S., Mudigere, D., Nocedal, J., Smelyanskiy, M., & Tang, P. T. P. (2017). On large-batch training for deep learning: Generalization gap and sharp minima. In International Conference on Learning Representations (ICLR).
Link: https://arxiv.org/abs/1609.04836
