# A Graph-Based Framework for User-Level Feature Modeling with Contextual Embeddings

## Dataset

This is PAN Dataset used in the project which don't have any User Level Features :

- [Data 1 MIB Dataset Link](http://mib.projects.iit.cnr.it/dataset.html)
  
- [Data 2 PAN Dataset Link](https://github.com/HamedBabaei/PAN2019_bots_gender_profiling)

- [Data 2 Saved Models Link](https://drive.google.com/drive/folders/1kIC9QREwYQOxwAp0h5NoSQxfbbBQ67Ke?usp=sharing)

You can download the dataset parts from the provided links.

### **MiB Dataset Comparison Results**

| Paper Name                                      | Accuracy | Class 0 Precision | Class 0 Recall | Class 0 F1-Score | Class 1 Precision | Class 1 Recall | Class 1 F1-Score |
|------------------------------------------------|----------|--------------------|----------------|------------------|-------------------|----------------|------------------|
| Detecting Bot Behaviour in Social Media using Digital DNA Compression | 0.984    | 0.985              | 0.983          | 0.984            | 0.982             | 0.98           | 0.981            |
| Bot Detection in Social Networks Using Stacked Generalization Ensemble | 0.989    | 0.995              | 0.992          | 0.9935           | 0.99              | 0.988          | 0.989            |
| Social Media Bot Detection with Deep Learning Methods: A Systematic Review | 0.952    | 0.947              | 0.943          | 0.945            | 0.94              | 0.937          | 0.9385           |
| Twitter Bot Detection and Ranking using Supervised Machine Learning Techniques | 0.978    | 0.973              | 0.971          | 0.972            | 0.968             | 0.965          | 0.9665           |
| Social Media Bot Detection with Deep Learning Methods: A Systematic Review | 0.965    | 0.962              | 0.96           | 0.961            | 0.958             | 0.957          | 0.9575           |
| **Our Model (Test Data Results)**              | **0.991** | **0.991**          | **0.998**      | **0.995**        | **0.989**         | **0.955**      | **0.972**        |
| **Our Model (Validation Data Results)**        | **0.989** | **0.989**          | **0.998**      | **0.993**        | **0.989**         | **0.944**      | **0.966**        |

---

### **PAN Dataset Comparison Results**

| Paper Name                                      | Accuracy | Class 0 Precision | Class 0 Recall | Class 0 F1-Score | Class 1 Precision | Class 1 Recall | Class 1 F1-Score |
|------------------------------------------------|----------|--------------------|----------------|------------------|-------------------|----------------|------------------|
| Overview of PAN 2019: Bots and Gender Profiling | 0.9595   | 0.97               | 0.965          | 0.9675           | 0.95              | 0.955          | 0.9525           |
| Author Profiling Using Semantic and Syntactic Features | 0.92      | 0.925              | 0.92           | 0.9225           | 0.915             | 0.918          | 0.9165           |
| Random Forest Classifier for Gender Profiling  | 0.84     | 0.85               | 0.845          | 0.8475           | 0.835             | 0.83           | 0.8325           |
| Using MLPs for Author Profiling                | 0.905    | 0.91               | 0.905          | 0.9075           | 0.905             | 0.9            | 0.9025           |
| Deep Learning with BiLSTM for Bots Detection   | 0.935    | 0.945              | 0.94           | 0.9425           | 0.932             | 0.93           | 0.931            |
| Hybrid Model: Combining SVM and LSTM for Author Profiling | 0.945    | 0.95               | 0.948          | 0.949            | 0.943             | 0.94           | 0.9415           |
| **Our Model (Testing Data Results)**           | **0.968** | **0.971**          | **0.967**      | **0.969**        | **0.965**         | **0.969**      | **0.968**        |
| **Our Model (Validation Data Results)**        | **0.967** | **0.968**          | **0.967**      | **0.968**        | **0.966**         | **0.966**      | **0.966**        |

## Ablation Study Results

| Ablation Scenario            | Accuracy | Class 0 Precision | Class 0 Recall | Class 0 F1-Score | Class 1 Precision | Class 1 Recall | Class 1 F1-Score |
|------------------------------|----------|-------------------|----------------|------------------|-------------------|----------------|------------------|
| Our Model (Test Data Results) | 0.991    | 0.991             | 0.998          | 0.995            | 0.989             | 0.955          | 0.972            |
| Without Statuses Count       | 0.950    | 0.946             | 0.985          | 0.965            | 0.935             | 0.910          | 0.922            |
| Without Followers Count      | 0.970    | 0.960             | 0.990          | 0.975            | 0.948             | 0.940          | 0.944            |
| Without Friends Count        | 0.960    | 0.954             | 0.988          | 0.971            | 0.940             | 0.920          | 0.930            |
| Without Favorites Count      | 0.935    | 0.932             | 0.976          | 0.954            | 0.911             | 0.901          | 0.905            |
| Without GraphSAGE            | 0.945    | 0.940             | 0.975          | 0.957            | 0.925             | 0.905          | 0.914            |

---

## Key Observations

1. **Overall Performance**
   - The full model achieved the highest performance with an accuracy of 0.991 and Class 1 F1-Score of 0.972.
   
2. **Feature Importance**
   - Removing **Statuses Count** caused a significant drop in performance, indicating its critical role in the model's predictive capability.
   - **Favorites Count** also had a high weightage, as removing it resulted in one of the lowest accuracy scores (0.935).

3. **GraphSAGE Contribution**
   - The GraphSAGE component plays an essential role in capturing graph-related dependencies. Without it, the accuracy dropped to 0.945, and Class 1 metrics were affected notably.

4. **User-Level Features**
   - Features such as **Statuses Count**, **Followers Count**, **Friends Count**, and **Favorites Count** are highly influential, as removing them caused significant performance degradation.

---

## Conclusion
The ablation study highlights the importance of user-level features and graph-based components in achieving high performance. The model’s robustness is significantly impacted when these key features are removed, reaffirming their necessity in the architecture.
---
