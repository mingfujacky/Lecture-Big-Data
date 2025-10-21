---
marp: true
theme: default
class: default
size: 16:9
paginate: true
header: 國立陽明交通大學 電子與光子學士學位學程
headingDivider: 1
style: |
  section::after {
    content: attr(data-marpit-pagination) '/' attr(data-marpit-pagination-total);
  }
  
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .columns img {
    width: 50%;
  }
  .middle-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .middle-grid img {
    width: 75%;
  }
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  .grid img {
    width: 100%;
  }
  .red-text {
    color: red;
  }
  
  .blue-text {
    color: blue;  
  }
  .yellow-text {
    color: yellow;  
  }

  .small-text {
    font-size: 0.50rem;
  }

---
# Machine Learning: a Data Modeling Technique
>Machine learning is a field of study that gives computers the ability to learn without being explicitly programmed

![bg right:40% w:90%](file/image/fig3_1.jpg)

# 廣義的 AI 人工智慧
![bg right:40% w:90%](https://viscovery.com/wp-content/uploads/2024/08/AI-ML-DL-Gen-AI-LLM-Diffusion-Model-zh.webp)
- 人工智慧是一個目標，一種概念，不全然是具體的執行方法。
- 人類期待電腦或機器能夠透過程式模仿人類的感知、理解與行動，進而完成只有人類智慧才能達成的事情。

# 機器學習
![bg right:40% w:90%](https://viscovery.com/wp-content/uploads/2024/08/AI-ML-DL-Gen-AI-LLM-Diffusion-Model-zh.webp)

透過演算法，使用大量資料進行訓練，訓練完成後會產生模型。未來當有新的資料，我們可以使用訓練產生的模型進行預測。
- 垃圾郵件分類
- 心臟病風險評估
- YouTube / Netflix 推薦你喜歡的內容
- 網購系統推薦商品給你

# 深度學習
![bg right:40% w:90%](https://viscovery.com/wp-content/uploads/2024/08/AI-ML-DL-Gen-AI-LLM-Diffusion-Model-zh.webp)

仿造人類大腦學習的方式，經由類神經網路，一層一層下去交互運算，最後判斷出結果，如同讓AI模仿小孩一樣去學習認貓咪
- 聊天機器人（自然語言生成）
- 文字生成圖像
- 人臉辨識 / 影像分類
- 語音辨識與合成
- 自駕車
- 醫療影像分析
- 自動翻譯

# 生成式AI
![bg right:40% w:90%](https://viscovery.com/wp-content/uploads/2024/08/AI-ML-DL-Gen-AI-LLM-Diffusion-Model-zh.webp)

讓AI成為會創作新內容的數位畫家和數位作家
  - 學生專屬家教
  - 文章總結，整理報告及重點分析
  - 自動生成簡報大綱及內容
  - 製作社群貼文
  - 智慧客服
  - 虛擬直播主

# AI 是從哪裡蹦出來的？

# 
![bg right:50%, w:85%](https://dahetalk.com/wp-content/uploads/2018/04/e4babae5b7a5e699bae685a7aie799bce5b195e58fb2.png)

# 
![bg right:80%, w:20%](file/image/AI_history_1.webp)

# 
![bg right:80%, w:20%](file/image/AI_history_2.webp)




# Machine Learning: a Data Modeling Technique
>Machine learning is a field of study that gives computers the ability to learn without being explicitly programmed

>Machine learning is the process by which a computer can work more accurately as it collects and learns from the more data it is given
![bg right:40% w:90%](file/image/fig3_1.jpg)

# Applications of Machine Learning
![bg right:60% w:90%](file/image/applications_of_machine_learning.png)

# Python Tools Used in Machine Learning: Scikit-learn
![bg right:60% w:90%](https://www.kdnuggets.com/wp-content/uploads/Rosidi_10_Essential_Python_Libraries_for_DS_in_2024_2.png)

# Types of Machine Learning
![bg right:60% w:90%](file/image/main_types_of_machine_learning.png)

# ML Modeling Process
Building model is to guess the <span class="blue-text">**target**</span> (response) variable. To do that, it relies on <span class="blue-text">**features**</span> (predictors)— things you already know 
The process includes:
- Feature engineering and model selection
- Training the model
- Model validation
- Applying the trained model

![bg right:50% w:90%](file/image/ml_workflow.png.webp)


# Feature engineering
>Feature Engineering is the process of transforming raw data into meaningful features that can be better understood and used by machine learning models.
Often you may need to consult an expert or the appropriate literature to come up with meaningful features.

Suppose we want to predict whether it will rain tomorrow <span class="blue-text">(Yes/No) **target**</span>.
* Raw data: 2025-08-19 14:35, Hsinchu, Temperature = 30.2, Humidity = 75%
* After feature engineering:
	•	*month = 8, hour = 14, is_weekend = 0*
	•	*city_Hsinchu = 1, city_Taipei = 0, city_Taichung = 0*
	•	*temperature = 30.2; humidity = 0.75*
👉 These structured <span class="blue-text">features</span> can now be used by a machine learning model.

# Select Model
Scikit-learn provides a various methods for classification, regression, clustering and dimensionality reduction tasks.
![bg right:60% w:90%](file/image/scikit_learn_map.svg)

# Train Model
- After feature engineering and model selection, the next step is to split data into training sets and testing sets
- Then, train model by training data set. This involves feeding the model with the features and the corresponding target values.
![bg right:40% w:90%](file/image/steps_to_build_a_model_with_scikit_learn.jpg)

# Validate Model
- Validation is a way to estimate how well the model will perform on unseen data. Not just on the training data.
- Error measure (how wrong the model is) and validation strategies would be designed
  - Error measure method: mean squared error (MSE), or accuracy
    - MSE measures how far off your numeric predictions are.
    -	Accuracy measures how often your categorical predictions are correct.
  - Validation strategies
    - holdout validation (截留驗證法): train once, test once (80% for training and 20% for testing) 
    - k-fold cross-validation(交叉驗證法): train many times on different splits, then average results

# Apply Model
- After validating the model, the final step is to apply it to new, unseen data to make predictions.
- This involves using the trained model to infer the target variable based on the features of the new data.

# Regression
Case study: Global Temperature Change Prediction
![bg right:40% w:90%](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Common_Era_Temperature.svg/1920px-Common_Era_Temperature.svg.png)

[`regression_temperature.ipynb`](file/code/regression_temperature.ipynb)

# Classification
Case study: Recognition of Handwritten Digits
![bg right:40% w:90%](https://upload.wikimedia.org/wikipedia/commons/2/27/MnistExamples.png)

[`recognition_handwritten_digits.ipynb`](file/code/recognition_handwritten_digits.ipynb)

# Clustering
Case study: Iris Flower Dataset
[`kmeans_iris.ipynb`](file/code/kmeans_iris.ipynb)

# Dimensionality Reduction
Case study: PCA on Wine Quality Dataset
[`pca_wine_quality.ipynb`](file/code/pca_wine_quality.ipynb)

# Summary
- Machine learning is a technique that allows computers to learn from data and make predictions or decisions without being explicitly programmed.
- The machine learning process involves feature engineering, model selection, training, validation, and application.
- Common types of machine learning include supervised learning (classification and regression), unsupervised learning (clustering and dimensionality reduction).
- Python's Scikit-learn library provides a wide range of tools for building and deploying machine learning models.

# Homework
HW4 - BMI prediction using regression model

# Review
# 1. What is the main goal of machine learning?
A. To explicitly program computers to perform specific tasks
B. To enable computers to learn from data and make predictions or decisions
C. To store large amounts of data efficiently
D. To visualize data in a more understandable way
# 2. Which of the following is NOT a step in the machine learning modeling process?
A. Feature engineering
B. Model selection
C. Data encryption
D. Model validation
# 3. In supervised learning, what is the difference between classification and regression?
A. Classification predicts continuous values, while regression predicts categorical labels
B. Classification predicts categorical labels, while regression predicts continuous values
C. Classification is used for clustering, while regression is used for dimensionality reduction
D. Classification and regression are the same
# 4. Which Python library is commonly used for building machine learning models?
A. NumPy
B. Pandas
C. Scikit-learn
D. Matplotlib
# 5. In model validation, what is the purpose of using k-fold cross-validation?
A. To train the model on the entire dataset without splitting
B. To evaluate the model's performance on different subsets of the data and reduce overfitting
C. To visualize the model's predictions
D. To encrypt the data for security purposes
# 6. Which of the following is an example of a regression problem?
A. Predicting whether an email is spam or not
B. Classifying images of handwritten digits
C. Predicting the price of a house based on its features
D. Grouping customers based on their purchasing behavior
# 7. What is the main purpose of feature engineering in machine learning?
A. To transform raw data into meaningful features that can be used by machine learning models
B. To encrypt the data for security purposes
C. To visualize the data in a more understandable way
D. To store large amounts of data efficiently
# 8. In the context of machine learning, what does the term "target variable" refer to?
A. The features used to make predictions
B. The variable that the model is trying to predict
C. The algorithm used to train the model
D. The validation strategy used to evaluate the model
# 9. Which of the following is NOT a common type of machine learning?
A. Supervised learning
B. Unsupervised learning
C. Reinforcement learning
D. Data encryption
# 10. What is the main advantage of using machine learning over traditional programming methods?
A. Machine learning can handle large amounts of data more efficiently
B. Machine learning can adapt and improve its performance as it learns from new data
C. Machine learning is easier to implement than traditional programming
D. Machine learning does not require any data to function
