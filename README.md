## Recommendation Algorithm Evaluation

This project evaluates five collaborative filtering algorithms on a filtered subset of the MovieLens dataset (userID and itemID ≤ 1000). The algorithms include:

- **SVD**
- **NMF**
- **SlopeOne**
- **CoClustering**
- **KNNBasic** (item-based, cosine similarity)

### Evaluation Approach

The dataset was processed using the `Surprise` library and evaluated via 3-fold cross-validation. Both **training** and **test** metrics (RMSE and MAE) were captured to compare prediction performance and assess overfitting.

### Results Summary

| Algorithm    | Train RMSE | Test RMSE | Train MAE | Test MAE |
|--------------|-------------|------------|------------|-----------|
| SVD          | 0.6554      | 0.8732     | 0.5135     | 0.6802    |
| NMF          | 0.6343      | 0.9110     | 0.4838     | 0.7065    |
| SlopeOne     | 0.7169      | 0.8782     | 0.5494     | 0.6816    |
| CoClustering | 0.8225      | 0.9155     | 0.6394     | 0.7131    |
| KNNBasic     | 0.8757      | 0.9672     | 0.6894     | 0.7634    |

### Insights

- **SVD** delivered the best test performance with the lowest RMSE and MAE.
- **SlopeOne** was nearly as good but had the smallest generalization gap, indicating minimal overfitting.
- **KNNBasic** had the highest error and significant overfitting, suggesting it’s less ideal for larger or sparse datasets in this configuration.
- **NMF** and **CoClustering** performed moderately, with slightly higher errors and generalization gaps.

### Visualization

Bar charts comparing **train vs test RMSE and MAE** helped visualize the performance and overfitting across models.

> ✅ For scalable, production-ready recommendations, **SVD** or **SlopeOne** are recommended depending on the balance of accuracy vs simplicity.
