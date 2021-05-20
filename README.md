# DeepFakes Detection 


Our DeepFake detection system was based on the composed stack of two models which were reshaped and tested individually based on the implementation given in [1-2], achieven both an accuracy of 80.0% on the intra-database. Given the feature space described for these two classifiers, where both yielded similar AUC under different hypertuning for the same classifier, we decided to treat them as individual classifiers. Therefore, the combination of its correspondent predicted probabilities were extracted for each case, and combined in several ways: 1) Obtaining the mean, 2) obtaining the weighted average, 3) predicting the best weights using a third classifier fed with the two scores as features. From these experiments, the weighted average of the individual scores obtained the best results using the test set. Other experiments involved combining both obtained features and testing multiple classifiers and feature reduction techniques, such as Principal Component Analysis and decision trees importance classification. This was useful during the dimensionality reduction for every model, because it allowed us to understand which features had the greatest impact on the binary classification task.

Results for  intra-database testing using UADFV database are shown on below. 
![](/img/table.png)

![](/img/models.png)


Authors: Sebastián Cajas, Julián Salazar, Zhanbota Bissaliyeva 

References: 

[1]  F. Matern, Ch.Riess, M.Stamminger, “Exploiting Visual Artifacts to Expose Deepfakes
and Face Manipulations”, Friedrich-Alexander University Erlangen-Nuremberg, 2019

[2] Durall, R., Keuper, M., Pfreundt, F. J., & Keuper, J. (2019). Unmasking deepfakes with
simple features. arXiv preprint arXiv:1911.00686. Github: 
