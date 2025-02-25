# ICSE2025

## Enhanced Detection of Code Vulnerability with Synergy between Data-Driven, Rule-Based and Unsupervised Learnings

Code vulnerability creates potential risks of compromising software security. While state-of-the-art approaches focus either on data-driven or rule-based models, this paper tends to learn code-based vulnerabilities more accurately through partnership of data-driven (deep learning) and rule-based learning processes, while leveraging unsupervised learning to prune the outcome of this hybrid learning process. The weaknesses of each method are compensated for, through leveraging the others strengths. The proposed approach, initially train a deep neural network, which encodes the source code into continuous vectors, while preserving code semantic-syntactic properties. Given the embedding vectors, a set of rules are governed by an ensemble classification method, namely random forest, which combines the output of multiple decision trees to reach an optimal classification accuracy. Finally, the least contributing trees to the final classification decisions are identified through a novel pruning algorithm and the exploitation of multiple clustering algorithms, preventing the model from overfitting to training data. We compared our method to several state-of-the-art rule-based, NN-based, pruning-based, and vulnerability detection methods in Java and C. The evaluation results surpassed the said algorithms' accuracy in classifying method-level vulnerabilities.

## Steps to reproduce

Dataset used- CrossVul dataset (Java) Devign dataset (C)

Training code2vec on Java language to generate code embeddings. For this purpose, we followed the readme of code2vec repo-https://github.com/tech-srl/code2vec Training code2vec on C language to generate code embeddings. For this purpose, we used the procedure specified in the reproduction package to retrain code2vec-https://figshare.com/s/284abfba67dba448fdc2 Generated embeddings were stored on the drive and used to work with our specified methodology in the paper.

The generated embeddings can be used directly and replaced in the code to get the embeddings and the rest of the algorithms can be applied as provided in .ipynb files.

The experimental results can be achieved by using this generated embedding and applying all the algorithms from .ipynb files a. CrossVul datasets experiments- Experiments were performed on bad and good code and can be seen in CodeVulnerabilityBigDataset and Code2vec+ML algorithms.ipynb files. To see the final results for this dataset with all the algorithms and our proposed algorithm check the FinalProposedModel_PrunedRF.ipynb file. All neural network testing can be found in NeuralNetworksTesting.ipynb file.

b. Devign datasets experiments- Experiments performed can be seen in Devign_CodeVulExperiments.ipynb which includes all the methods performed. All the above files include experiments for code2vec, codebert, Traditional ML algorithms such as Decision trees, Random forest, SVM, Naive bayes, gradient boosting, XGbbost, other Neural network algorithms, etc. Comparison between all the clustering algorithms is shown for the dataset that resulted in Table 8. in paper.

c. Other experiments- To test our proposed algorithm on the common datasets we also experimented on a cancer dataset, a multiclassification dataset, and a dataset with more than 10k records. Though this is unrelated to the software engineering domain, it will provide evidence of how efficiently our algorithm works.

Comparison between different clustering-based pruning techniques is also provided in Pruned_RF_ResearchPapers_Implementation.ipynb

All the results mentioned in the paper are experimented with and provided here.

The latest change to the code is the embeddings generated by the Devign dataset which consists of 27247 embeddings by reimplementing the version specified in https://github.com/dcoimbra/dx2021. These embeddings can be found in merged_file_devign zip folder. This file can be downloaded and run against our proposed algorithm provided in the experimental file-DevignCompleteDataset.ipynb file. The PrunedRF results can be seen in the same file achieving accuracy greater than 95% for all the clustering algorithms.
