# Rebuttal

## Reviewer ysaA Scores：4，3

![057d5dc9f57ea12ec1cbfc66eed2f4f](C:\Users\zhuqh\Documents\WeChat Files\wxid_8gjl1iff2d6922\FileStorage\Temp\057d5dc9f57ea12ec1cbfc66eed2f4f.png)

Dear Reviewer ysaA,

Thank you very much for your constructive comments and suggestions on our manuscript titled "BATTLE: Unsupervised Bi-Level Optimization with Implicit Relationship Mining for Attributed Graph Anomaly Detection" with Submission ID 732. We have carefully considered each point and have made significant revisions to address your concerns. Below, we provide a detailed response to your questions.

Thank you for your question regarding the key concerns. The reason we did not include the F1 score comparison is mainly due to the limitation on the length of the paper; however, we do have the relevant data.

Below is our related data Table:

| Methods         | BlogCatalog F1@50 | BlogCatalog F1@100 | Flickr F1@50 | Flickr F1@100 | Pubmed F1@50 | Pubmed F1@100 |
| --------------- | ----------------- | ------------------ | ------------ | ------------- | ------------ | ------------- |
| Radar(2017)     | 0.183             | 0.345              | 0.141        | 0.246         | 0.086        | 0.143         |
| ANOMALOUS(2018) | 0.179             | 0.336              | 0.155        | 0.260         | 0.094        | 0.159         |
| DOMINANT(2020)  | 0.221             | 0.357              | 0.151        | 0.264         | 0.107        | 0.179         |
| DeepAE(2020)    | 0.192             | 0.336              | 0.141        | 0.260         | 0.098        | 0.170         |
| Deep2NAD(2021)  | 0.133             | 0.302              | 0.151        | 0.270         | 0.098        | 0.170         |
| HCM(2022)       | 0.224             | 0.367              | 0.163        | 0.278         | 0.107        | 0.180         |
| ANEMONE(2021)   | 0.225             | 0.367              | 0.160        | 0.272         | 0.102        | 0.172         |
| CoLA(2022)      | 0.192             | 0.317              | 0.130        | 0.227         | 0.113        | 0.184         |
| Sub-CR(2022)    | 0.238             | 0.375              | 0.167        | 0.278         | 0.116        | 0.191         |
| LCUnpool(2023)  | 0.233             | 0.375              | 0.163        | 0.283         | 0.114        | 0.186         |
| BATTLE(ours)    | **0.246**         | **0.382**          | **0.168**    | **0.284**     | **0.120**    | **0.197**     |

**Question 1 Respond:**

We greatly appreciate your inquiry regarding the scalability of our BATTLE framework to large-scale graphs. It is a valid point, and we acknowledge the importance of assessing the performance of our framework on large graphs with high-dimensional attributes.

First and foremost, we would like to emphasize that, conceptually, there is no inherent distinction between large graphs and the smaller ones we have included in our current dataset. The primary variance lies in the magnitude of computational resources required to process them.While we have indeed contemplated conducting validations on larger graphs, our current computational resources are unfortunately limited, which has restricted our ability to perform such extensive experiments at this stage.

Nevertheless, based on the structural similarities between large and small graphs, we are confident that the BATTLE framework, which has demonstrated robust performance on smaller graphs, should exhibit similar efficacy when scaled up, provided that sufficient computational resources are available.

We are actively seeking to expand our computational capabilities to address this limitation and are committed to validating the scalability of our framework in future work. We believe that with the appropriate resources, the BATTLE framework will prove to be equally effective on larger graphs, maintaining its performance integrity.

**Question 2 Respond:** 

Thank you for your constructive feedback. We understand the importance of using real-world examples to validate the effectiveness of our BATTLE framework. While the anomalies in the public datasets we used are indeed artificially introduced, and previous studies have relied on these datasets for validation, we chose to continue using them to ensure the validity and fairness of our experiments.

Your suggestion is very helpful, and we agree that real-world examples would provide a stronger validation of our framework. However, due to the current lack of publicly available real-world datasets related to our field of study, we have been limited in this regard and have not been able to conduct such validations. We will definitely consider this point in our future work and aim to incorporate more real-world examples for further validation when they become available or when we are able to access them.

**Question 3 Respond:**

Thanks for your question. The primary contribution of BATTLE lies in incorporating implicit relationship into anomaly detection. Regarding the complexity of BATTLE, which comes mainly from the attention network learner, sparsification, graph convolutional network layer, contrastive loss, and implicit relationship prediction. We calculated the complexity of BATTLE as 

$$
O\left(nd(L_1 + b_1) + md_1L + nd_2^1L + nd_2^2L + m^2 + (2 + R)n^2\right)
$$

where \( n(m) \) is the number of nodes(edges), \( b_1 \) is the batch size of attention network. \( d/d_1/d_2 \) are the dimension of node attribute/representation/projection, \( L_1/L \) is the layer number of attention network and GCN, and \( R \) is the number of graph samples. Compared to ANEMONE (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 6n^2\right)
$$

), CoLA (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 4n^2 + c^2nR\right)
$$

), and Sub-CR (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 5n^2 + n^2R\right)
$$

), our method does not have significantly higher complexity (all four methods are in \( O(n^2) \) order of magnitude), yet we achieve notable performance improvement. We will present the computational details of model complexity in the final version. Additionally, we conducted experiments comparing BATTLE with other baselines regarding computational efficiency. As shown in Table 1, the experimental results demonstrate that BATTLE does not significantly increase training time compared to several other methods. However, we achieve notable performance improvement.

**Table 1:** Training time for different methods

| Methods       | BlogCatalog | Flickr    |
| ------------- | ----------- | --------- |
| ANEMONE(2021) | 10.07 min   | 22.40 min |
| CoLA(2022)    | 9.35 min    | 20.60 min |
| Sub-CR(2022)  | 10.90 min   | 23.62 min |
| BATTLE(Ours)  | 11.71 min   | 25.04 min |

**Question 4 Respond:**

Thank you very much for your question. We are seriously considering incorporating significance tests into our analysis. However, due to time constraints, we may not be able to complete the relevant experiments within this rebuttal round. We will do our utmost to present the results to you in the next rebuttal round. In the meantime, you may refer to the initial comparison of F1 scores that I presented above.

We believe that these revisions have significantly improved the quality and clarity of our paper. We are confident that BATTLE provides a valuable contribution to the field and is worthy of presentation at WWW25.

Thank you once again for your thorough review and for giving us the opportunity to improve our work. We look forward to the possibility of presenting our research at WWW25.

## Reviewer 5u3k Scores：5，5

![4aa8c1910d4c8e422447ab5c165ae34](C:\Users\zhuqh\Documents\WeChat Files\wxid_8gjl1iff2d6922\FileStorage\Temp\4aa8c1910d4c8e422447ab5c165ae34.png)

Dear Reviewer 5u3k ,

Thank you very much for your constructive comments and suggestions on our manuscript titled "BATTLE: Unsupervised Bi-Level Optimization with Implicit Relationship Mining for Attributed Graph Anomaly Detection" with Submission ID 732. We have carefully considered each point and have made significant revisions to address your concerns. Below, we provide a detailed response to your questions.

**Question 1 Respond:**

Thank you for your question. Indeed, validation with large graphs and real-world data is essential, and we have considered conducting such validations. However, due to practical constraints, we have not been able to carry out the relevant experiments.

For large graphs, we would like to emphasize that, conceptually, there is no inherent distinction between large graphs and the smaller ones we have included in our current dataset. The primary variance lies in the magnitude of computational resources required to process them. While we have indeed contemplated conducting validations on larger graphs, our current computational resources are unfortunately limited, which has restricted our ability to perform such extensive experiments at this stage. Nevertheless, based on the structural similarities between large and small graphs, we are confident that the BATTLE framework, which has demonstrated robust performance on smaller graphs, should exhibit similar efficacy when scaled up, provided that sufficient computational resources are available.

We are actively seeking to expand our computational capabilities to address this limitation and are committed to validating the scalability of our framework in future work. We believe that with the appropriate resources, the BATTLE framework will prove to be equally effective on larger graphs, maintaining its performance integrity.

Regarding real-world data, having examples from the real world would indeed provide a better validation of the effectiveness of our BATTLE framework. However, due to the current lack of publicly available real-world datasets relevant to our study, we have been constrained and have not been able to conduct such validations.

Your inquiry is very helpful for our work, and we will definitely take this into account in future studies, attempting to include validations for large graphs and real-world data.

**Question 2 Respond:** 

Thanks for your question. The primary contribution of BATTLE lies in incorporating implicit relationship into anomaly detection. Regarding the complexity of BATTLE, which comes mainly from the attention network learner, sparsification, graph convolutional network layer, contrastive loss, and implicit relationship prediction. We calculated the complexity of BATTLE as 

$$
O\left(nd(L_1 + b_1) + md_1L + nd_2^1L + nd_2^2L + m^2 + (2 + R)n^2\right)
$$

where \( n(m) \) is the number of nodes(edges), \( b_1 \) is the batch size of attention network. \( d/d_1/d_2 \) are the dimension of node attribute/representation/projection, \( L_1/L \) is the layer number of attention network and GCN, and \( R \) is the number of graph samples. Compared to ANEMONE (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 6n^2\right)
$$

), CoLA (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 4n^2 + c^2nR\right)
$$

), and Sub-CR (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 5n^2 + n^2R\right)
$$

), our method does not have significantly higher complexity (all four methods are in \( O(n^2) \) order of magnitude), yet we achieve notable performance improvement. We will present the computational details of model complexity in the final version. Additionally, we conducted experiments comparing BATTLE with other baselines regarding computational efficiency. As shown in Table 1, the experimental results demonstrate that BATTLE does not significantly increase training time compared to several other methods. However, we achieve notable performance improvement.

**Table 1:** Training time for different methods

| Methods       | BlogCatalog | Flickr    |
| ------------- | ----------- | --------- |
| ANEMONE(2021) | 10.07 min   | 22.40 min |
| CoLA(2022)    | 9.35 min    | 20.60 min |
| Sub-CR(2022)  | 10.90 min   | 23.62 min |
| BATTLE(Ours)  | 11.71 min   | 25.04 min |

**Question 3 Respond:**

case study



We believe that these revisions have significantly improved the quality and clarity of our paper. We are confident that BATTLE provides a valuable contribution to the field and is worthy of presentation at WWW25.

Thank you once again for your thorough review and for giving us the opportunity to improve our work. We look forward to the possibility of presenting our research at WWW25.

Sincerely,

xxx

## Reviewer 1Mrj Scores：3，3

![ddee7d434dc0f497cfda2edfa32d333](C:\Users\zhuqh\Documents\WeChat Files\wxid_8gjl1iff2d6922\FileStorage\Temp\ddee7d434dc0f497cfda2edfa32d333.png)

Dear Reviewer 1Mrj,

Thank you very much for your constructive comments and suggestions on our manuscript titled "BATTLE: Unsupervised Bi-Level Optimization with Implicit Relationship Mining for Attributed Graph Anomaly Detection" with Submission ID 732. We have carefully considered each point and have made significant revisions to address your concerns. Below, we provide a detailed response to your questions.

**Question 1 Respond:**

Thank you for your questions. Firstly, regarding the first point you mentioned about BATTLE's robustness to incoherent local structures or noise, we have addressed this in Section 4.4 "Ablation Study (RQ3)" of our paper. We appreciate your mention of the potential issue of incoherent local structures or noise, which is indeed present in relational graphs. However, we have demonstrated that incorporating implicit relationships is more effective than relying solely on explicit relationships, indicating that our BATTLE framework is robust against potential noise.

Our implicit relationship graph adds auxiliary edges to the original graph (which only contains explicit relationships) to represent the hidden, potential semantic relationships between entities. In other words, implicit relationships serve as auxiliary information, and we ultimately combine explicit and implicit relationships. In the experiments of Section 4.4, we designed three variants of BATTLE to compare their performance in anomaly detection tasks:

1. **BATTLE-Origin**: Uses only the original graph (i.e., explicit relationships) for anomaly detection.
2. **BATTLE-Mixed**: Uses both the original graph and the implicit relationship graph for anomaly detection.
3. **BATTLE-Implicit**: Uses only the implicit relationship graph for anomaly detection.

The results show that compared to BATTLE-Origin, BATTLE-Mixed improved the Precision@50 metric by 5.2% and 3.2% on two datasets, while BATTLE-Implicit improved the Precision@50 metric by 10% and 7.4% on the same two datasets. These results substantiate the effectiveness of constructing implicit edges. In other words, in response to the potential incoherent local structures or noise you mentioned, our BATTLE is indeed robust, as the inclusion of implicit relationships outperforms the original explicit relationships alone.

**Question 2 Respond:** 

The total training time for our BATTLE framework is approximately 35 hours. The bi-level optimization method proposed in Section 3.3 can reduce the training time of BATTLE in the following ways:

1. **Explicit Dependency Modeling**: The bi-level optimization method models the dependencies between the upper-level task (implicit relationship mining) and the lower-level task (anomaly detection on attributed networks) explicitly, making the optimization process more direct and efficient. This approach can reduce unnecessary iterations because it allows the model to update parameters more precisely, reflecting the complex coupling between the two tasks.

2. **Parameter Update Strategy**: In bi-level optimization, by calculating the gradient of the best-response constraint (Best-Response Gradient), the model can update parameters more effectively. This strategy may reduce the number of iterations required in traditional optimization methods because it optimizes directly for the dependencies between the upper and lower tasks.

3. **Reducing Redundant Computations**: To address the high computational complexity in traditional bi-level optimization, BATTLE designs an implicit gradient scheme, combined with outer-product Hessian approximation as a fast solution strategy. This method avoids the explicit computation of the Hessian matrix and its inverse, thereby reducing computational load and training time. By using implicit gradient estimation (Implicit Gradient Estimation) and outer-product approximation (Outer-Product Approximation) methods, the BATTLE framework can simplify second-order derivatives to first-order derivatives, thus reducing computational complexity in the solution process. This approach can reduce the consumption of computational resources, potentially reducing training time.

   1. **Implicit Gradient Estimation**:
      $$
      \text{GR} = \left( \frac{\partial F}{\partial \theta_D} \right)^\top B,  \quad \frac{\partial^2 f}{\partial \theta_D \partial \theta_D} B = - \frac{\partial F}{\partial \theta_D}
      $$
      Here, **GR** represents the hierarchical coupled-response gradient term, and **B** is a linear solution system used to avoid direct computation of the Hessian matrix and its inverse.

   2. **Outer-Product Approximation**:
      $$
      \frac{\partial^2 f}{\partial \theta_D \partial \theta_D} \approx \left( \frac{\partial f}{\partial \theta_D} \right) \left( \frac{\partial f}{\partial \theta_D} \right)^\top, \quad \frac{\partial^2 f}{\partial \theta_D \partial \theta_G} \approx \left( \frac{\partial f}{\partial \theta_D} \right) \left( \frac{\partial f}{\partial \theta_G} \right)^\top
      $$
      Here, by using outer-product approximation, the computation of second-order derivatives is simplified to the product of first-order derivatives.

These formulas demonstrate how implicit gradient estimation and outer-product approximation can simplify complex  second-order derivative computations, thereby reducing the complexity and memory consumption of the algorithm.

**Question 3 Respond:**

Thank you for your constructive feedback. The anomalies in the public datasets we used are indeed artificially introduced, and previous studies have validated their work using these datasets. To ensure the effectiveness of our BATTLE framework and the fairness of our experiments, we have chosen to continue using these widely adopted public datasets.

Your suggestion is very helpful; having examples from the real world would indeed provide stronger validation for our BATTLE framework. However, due to the current lack of publicly available real-world datasets, we are limited in this regard and have not been able to conduct such validations. We will consider this point in future work and attempt to incorporate more real-world examples for further validation.

We believe that these revisions have significantly improved the quality and clarity of our paper. We are confident that BATTLE provides a valuable contribution to the field and is worthy of presentation at WWW25.

Thank you once again for your thorough review and for giving us the opportunity to improve our work. We look forward to the possibility of presenting our research at WWW25.

Sincerely,

xxx

## Reviewer jpAn Scores：5，6

![4a01eb65c021721d7e1fc0637441278](C:\Users\zhuqh\Documents\WeChat Files\wxid_8gjl1iff2d6922\FileStorage\Temp\4a01eb65c021721d7e1fc0637441278.png)

Dear Reviewer jpAn ,

Thank you very much for your constructive comments and suggestions on our manuscript titled "BATTLE: Unsupervised Bi-Level Optimization with Implicit Relationship Mining for Attributed Graph Anomaly Detection" with Submission ID 732. We have carefully considered each point and have made significant revisions to address your concerns. Below, we provide a detailed response to your questions.

**Question 1 Respond:**

Thank you very much for your suggestion. We have made the corresponding modifications in the paper.

**Question 2 Respond:** 

Thank you very much for your suggestion. We have made the corresponding modifications in the paper.

**Question 3 Respond:**

Thank you for your suggestion, and we appreciate your understanding regarding the space constraints in the paper. Below is the explanation of how anomalies were injected into the datasets:

As anomalies are rarely directly labeled in real-world datasets, anomaly injection methods are necessary to evaluate the performance of anomaly detection algorithms. In Section 5.1 "Datasets" of the paper, we mentioned using two common anomaly injection methods for the three benchmark datasets (BlogCatalog, Flickr, and Pubmed):

1. **Structural Anomaly Injection**:
   - Structural anomalies refer to abnormalities injected into the network structure, which may involve modifying the connectivity within the network, such as adding or removing edges, to simulate the actions of attackers or malicious actors who create or disrupt connections within the network.

2. **Attribute Anomaly Injection**:
   - Attribute anomalies refer to abnormalities injected into the attributes of network nodes, which may involve altering the attribute values of nodes to simulate data tampering by attackers or inconsistencies caused by system errors.

These injection methods allow us to assess the effectiveness of our BATTLE framework in detecting anomalies under various conditions that mimic real-world scenarios. We hope this explanation provides clarity on our approach to dataset preparation for anomaly detection tasks.

**Question 4 Respond:**

case study

**Question 5 Respond:**

Thanks for your question. The primary contribution of BATTLE lies in incorporating implicit relationship into anomaly detection. Regarding the complexity of BATTLE, which comes mainly from the attention network learner, sparsification, graph convolutional network layer, contrastive loss, and implicit relationship prediction. We calculated the complexity of BATTLE as 

$$
O\left(nd(L_1 + b_1) + md_1L + nd_2^1L + nd_2^2L + m^2 + (2 + R)n^2\right)
$$

where \( n(m) \) is the number of nodes(edges), \( b_1 \) is the batch size of attention network. \( d/d_1/d_2 \) are the dimension of node attribute/representation/projection, \( L_1/L \) is the layer number of attention network and GCN, and \( R \) is the number of graph samples. Compared to ANEMONE (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 6n^2\right)
$$

), CoLA (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 4n^2 + c^2nR\right)
$$

), and Sub-CR (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 5n^2 + n^2R\right)
$$

), our method does not have significantly higher complexity (all four methods are in \( O(n^2) \) order of magnitude), yet we achieve notable performance improvement. We will present the computational details of model complexity in the final version. Additionally, we conducted experiments comparing BATTLE with other baselines regarding computational efficiency. As shown in Table 1, the experimental results demonstrate that BATTLE does not significantly increase training time compared to several other methods. However, we achieve notable performance improvement.

**Table 1:** Training time for different methods

| Methods       | BlogCatalog | Flickr    |
| ------------- | ----------- | --------- |
| ANEMONE(2021) | 10.07 min   | 22.40 min |
| CoLA(2022)    | 9.35 min    | 20.60 min |
| Sub-CR(2022)  | 10.90 min   | 23.62 min |
| BATTLE(Ours)  | 11.71 min   | 25.04 min |



We believe that these revisions have significantly improved the quality and clarity of our paper. We are confident that BATTLE provides a valuable contribution to the field and is worthy of presentation at WWW25.

Thank you once again for your thorough review and for giving us the opportunity to improve our work. We look forward to the possibility of presenting our research at WWW25.

Sincerely,

xxx

## Reviewer 7c2i  Scores：5，6

![bd314c8ffcdaa360a317b59a1ff44cc](C:\Users\zhuqh\Documents\WeChat Files\wxid_8gjl1iff2d6922\FileStorage\Temp\bd314c8ffcdaa360a317b59a1ff44cc.png)

Dear Reviewer 7c2i ,

Thank you very much for your constructive comments and suggestions on our manuscript titled "BATTLE: Unsupervised Bi-Level Optimization with Implicit Relationship Mining for Attributed Graph Anomaly Detection" with Submission ID 732. We have carefully considered each point and have made significant revisions to address your concerns. Below, we provide a detailed response to your questions.

**Question 1 Respond:**

Thank you for your question. Below, I will elaborate on the necessity of incorporating implicit relationship mining into anomaly detection:

1. **Providing a New Perspective**: Implicit relationship mining offers a new relational-level perspective for anomaly detection. In real-world attributed networks, there are not only explicit relationships (i.e., direct connections) but also implicit relationships (i.e., potential, indirect connections). These implicit relationships can reflect the underlying reasons for entities establishing explicit connections, which is crucial for understanding complex interactions within networks and identifying anomalous patterns.

2. **Revealing Underlying Motivations**: Implicit relationships can reveal the underlying motivations for entities to form connections. For instance, in social networks, two users might connect due to shared interests or mutual friendships; these implicit relationships are essential for differentiating the behavior patterns of normal users from malicious users, such as spammers or fraudsters.

3. **Enhancing Detection Accuracy**: By considering implicit relationships, anomaly detection models can more accurately capture anomalous patterns within networks. Many anomalous patterns, such as the spread of false information, are often created by malicious users lacking the genuine motivations and implicit connections that accompany legitimate interactions. Implicit relationship mining helps identify these anomalous patterns, thereby enhancing the accuracy of anomaly detection.

4. **Strengthening Model Robustness**: Implicit relationship mining allows models to better understand the complex interplay between network structure and node attributes, which helps improve the model's robustness in the face of various network attacks and anomalous situations.

5. **Compensating for the Insufficiency of Explicit Relationships**: In some cases, relying solely on explicit relationships may not fully capture all the important information within a network. Implicit relationship mining can supplement the information not covered by explicit relationships, providing a more comprehensive network representation, which is particularly important for anomaly detection.

6. **Addressing Real-World Challenges**: Real-world networks often contain complex and diverse implicit relationships that are not limited to specific types of implicit relationships (such as emotional relationships, advisor-advisee relationships, etc.). Designing a versatile method capable of mining various types of implicit relationships is key to solving the problem of anomaly detection in attributed networks.

**Question 2 Respond:** 

Thanks for your question. The primary contribution of BATTLE lies in incorporating implicit relationship into anomaly detection. Regarding the complexity of BATTLE, which comes mainly from the attention network learner, sparsification, graph convolutional network layer, contrastive loss, and implicit relationship prediction. We calculated the complexity of BATTLE as 

$$
O\left(nd(L_1 + b_1) + md_1L + nd_2^1L + nd_2^2L + m^2 + (2 + R)n^2\right)
$$

where \( n(m) \) is the number of nodes(edges), \( b_1 \) is the batch size of attention network. \( d/d_1/d_2 \) are the dimension of node attribute/representation/projection, \( L_1/L \) is the layer number of attention network and GCN, and \( R \) is the number of graph samples. Compared to ANEMONE (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 6n^2\right)
$$

), CoLA (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 4n^2 + c^2nR\right)
$$

), and Sub-CR (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 5n^2 + n^2R\right)
$$

), our method does not have significantly higher complexity (all four methods are in \( O(n^2) \) order of magnitude), yet we achieve notable performance improvement. We will present the computational details of model complexity in the final version. Additionally, we conducted experiments comparing BATTLE with other baselines regarding computational efficiency. As shown in Table 1, the experimental results demonstrate that BATTLE does not significantly increase training time compared to several other methods. However, we achieve notable performance improvement.

**Table 1:** Training time for different methods

| Methods       | BlogCatalog | Flickr    |
| ------------- | ----------- | --------- |
| ANEMONE(2021) | 10.07 min   | 22.40 min |
| CoLA(2022)    | 9.35 min    | 20.60 min |
| Sub-CR(2022)  | 10.90 min   | 23.62 min |
| BATTLE(Ours)  | 11.71 min   | 25.04 min |

Besides, validation on large-scale graphs is very important, and we have considered conducting such validations. However, our computational resources are limited and do not currently support the verification work required for large-scale graphs. While large graphs and the smaller graphs in our current datasets do not have any fundamental structural differences, large graphs do require more computational resources to complete experiments. Therefore, we believe that under conditions of sufficient computational resources, our BATTLE framework should also perform well on large graphs.

Your inquiry is very helpful to our work, and we will definitely take this into account in future studies, attempting to include validations for large-scale graphs.

**Question 3 Respond:**

Thank you for your question. Indeed, incorporating implicit relationships does alter the topology of the graph, but as demonstrated in our experiments, such changes lead to improved outcomes.

Our implicit relationship graph adds auxiliary edges to the original graph, which only contains explicit relationships, to represent the hidden, potential semantic relationships between entities. In other words, implicit relationships serve as auxiliary information, and we ultimately combine explicit and implicit relationships. In the experiments of Section 4.4, we designed three variants of BATTLE to compare their performance in anomaly detection tasks:

1. **BATTLE-Origin**: Uses only the original graph (i.e., explicit relationships) for anomaly detection.
2. **BATTLE-Mixed**: Uses both the original graph and the implicit relationship graph for anomaly detection.
3. **BATTLE-Implicit**: Uses only the implicit relationship graph for anomaly detection.

The results show that compared to BATTLE-Origin, BATTLE-Mixed improved the Precision@50 metric by 5.2% and 3.2% on two datasets, while BATTLE-Implicit improved the Precision@50 metric by 10% and 7.4% on the same two datasets. These results substantiate the effectiveness of constructing implicit edges. In other words, in response to the potential incoherent local structures or noise you mentioned, our BATTLE framework is indeed robust, as the inclusion of implicit relationships outperforms the original explicit relationships alone.

**Question 4 Respond:**

Below is a detailed response to the questions you've raised:

**Differences and Comparisons between BATTLE-Origin, BATTLE-Mixed, and BATTLE-Implicit**

1. **BATTLE-Origin**:
   - This variant uses only the original graph (i.e., explicit relationships only) for anomaly detection. It does not consider implicit relationships and relies solely on the direct connections in the network and node attributes.

2. **BATTLE-Mixed**:
   - This variant combines the original graph with the implicit relationship graph for anomaly detection. This approach aims to enhance the performance of anomaly detection by leveraging both explicit and implicit relationships.

3. **BATTLE-Implicit**:
   - This variant uses only the implicit relationship graph for anomaly detection. It entirely depends on the implicit relationship network obtained through graph contrastive learning and implicit relationship mining.

**Reasons for BATTLE-Mixed's Inferior Performance**

- **Complexity of Information Integration**: BATTLE-Mixed attempts to utilize both explicit and implicit relationships simultaneously, which may increase the model's complexity. If the integration of these two types of information is not well-coordinated, it could lead to a decrease in performance as the model might struggle to learn and utilize these different types of relationships effectively.

- **Weight Allocation Issues**: When combining explicit and implicit relationships, how to balance their contributions is a critical issue. If the model does not effectively allocate weights, it could result in the loss of important information or an increase in noise.

**Discussion on BATTLE-Joint and BATTLE-Alternative**

1. **BATTLE-Joint**:
   - This variant is trained using traditional joint optimization methods, which aim to optimize two complementary modules (implicit relationship mining and anomaly detection) simultaneously. However, this approach may not effectively capture the complex dependency between the two tasks, leading to suboptimal performance.

2. **BATTLE-Alternative**:
   - This variant is trained using a simpler alternating optimization strategy, where learning occurs at static positions between two tasks. This method may ignore the dynamic coupling relationships between tasks, thereby affecting performance.



We believe that these revisions have significantly improved the quality and clarity of our paper. We are confident that BATTLE provides a valuable contribution to the field and is worthy of presentation at WWW25.

Thank you once again for your thorough review and for giving us the opportunity to improve our work. We look forward to the possibility of presenting our research at WWW25.

Sincerely,

xxx