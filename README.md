# experimental records
## v1
![Alt text](./readme_resource/流程图.png)
### 默认参数结果
1. [回归数据集结果](./v1/results_standard_version/regression.xlsx)
2. [分类数据集结果](./v1/results_standard_version/classification.xlsx)
3. [系数r的可视化](./v1/results_standard_version/heatmap_standard_R/)
4. [phase1中distance matric可视化](./v1/results_standard_version/heatmap_standard_phase1_DistMap/)
5. [hidden representaion可视化](./v1/results_standard_version/tsne_hid/):分别对phase1模型输出的hidden representaion,phase2模型输出的hidden representaion，以及$\sum{r_k\beta_k}$使用t-sne可视化
6. 数据记录以及可视化
[可视化数据(phase1的hidden representaion,topic,distance matrix)](./v1/results_standard_version/data_visuliztion_standard/)
### 随机生成topics
原本设置:使用kmeans对输入样本聚类，使用聚类中心初始化topics
当前实验设置:使用随机数随机生成topics
1. [回归数据集结果](./v1/results_randomly_initialized_topics/regression.xlsx)
2. [分类数据集结果](./v1/results_randomly_initialized_topics/classification.xlsx)
3. [系数r的可视化](./v1/results_randomly_initialized_topics/heatmap_random_R/)
### 第一阶段使用mse
原本设置:phase1阶段$min(OT_{distance}(\vec{h},\sum{r_k\beta_k}))$(batch层次)<br>
当前实验设置:phase1阶段$min(MSE(\vec{h},\sum{r_k\beta_k}))$<br>
1. [回归数据集结果](./v1/results_mse_in_phase1/regression.xlsx)
2. [分类数据集结果](./v1/results_mse_in_phase1/classification.xlsx)
3. [系数r的可视化](./v1/results_mse_in_phase1/heatmap_mse_in_phase1/)
### 第二阶段使用ot
原本设置:phase2阶段$$min(MSE(\vec{h},\sum{r_k\beta_k}))$$<br>
当前实验设置:phase2阶段$$min(OT_{distance}(\vec{h},\sum{r_k\beta_k}))$$(batch层次)<br>
1. [回归数据集结果](./v1/results_ot_in_phase2/regression.xlsx)
2. [分类数据集结果](./v1/results_ot_in_phase2/classification.xlsx)
### 第一阶段使用mse与第二阶段使用ot结果比较
1. [回归数据集结果](./v1/result_mse_ot_compare/regression.xlsx)
2. [分类数据集结果](./v1/result_mse_ot_compare/classification.xlsx)
### 减小第一阶段的patience
原本设置:phase1的patience=16<br>
当前实验设置:phase1的patience=6<br>
1. [回归数据集结果](./v1/results_half_patience_in_phase1/regression.xlsx)
2. [分类数据集结果](./v1/results_half_patience_in_phase1/classification.xlsx)
### 将数据集改为平衡数据集
结果分别为在1. 在不平衡测试集上测试，2. 在平衡测试集上测试<br>
1. [数据集结果](./v1/results_balanced_dataset/classification.xlsx)
### 数据预处理之前使用kmeans聚类生成聚类中心，映射至高维作为初始topic
原本设置:先对训练集预处理，然后使用kmeans聚类，在将聚类中心映射至高维初始化topic<br>
当前实验设置:不经过预处理直接对训练集使用kmeans聚类，在将聚类中心映射至高维初始化topic，再预处理训练集<br>
1. [回归数据集结果](./v1/results_kmeans_before_preprocessing/regression.xlsx)
2. [分类数据集结果](./v1/results_kmeans_before_preprocessing/classification.xlsx)
## v2
(phase1只使用estimator预测y，estimator为MLP)<br>
一阶段只使用estimator<br>
### 使用MSE对齐hidden representaion与projection
1. [回归数据集结果](./v2/results_MSE/regression.xlsx)
2. [分类数据集结果](./v2/results_MSE/classification.xlsx)
### 使用OT对齐hidden representaion与projection
1. [回归数据集结果](./v2/results_OT/regression.xlsx)
2. [分类数据集结果](./v2/results_OT/classification.xlsx)
### 将projection作为pseodu_label结果
1. [回归数据集结果](./v2/results_pesudo_label/regression.xlsx)
2. [分类数据集结果](./v2/results_pesudo_label/classification.xlsx)
## v3
(v2基础上phase1的estimator结构与phase2结构相同)<br>
### 将projection作为pseodu_label结果
1. [回归数据集结果](./v3/pseudo_label/regression.xlsx)
2. [分类数据集结果](./v3/pseudo_label/classification.xlsx)
3. [数据记录以及可视化](./v3/pseudo_label/data_visulization/)
# ------
2024/1/22 update<br>
[v3](#v3)
实验结构:v2基础上，phase1的estimator结构与phase2结构相同<br>
实验数据：将phase的r*topic作为phase2的pseudo label的实验结果<br>
# ------
2024/1/21 update<br>
[v2](#v2)<br>
[v1中第一阶段使用mse与第二阶段使用ot结果比较](#第一阶段使用mse与第二阶段使用ot结果比较)<br>
[v1中标准方法(phase1 ot,phase2 mse)phase1数据记录(hidden representaion,topic,distance_matrix):v1-默认参数结果-6](#默认参数结果)<br>
   
