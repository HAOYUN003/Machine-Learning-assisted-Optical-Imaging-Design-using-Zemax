# Machine-Learning-assisted-Optical-Imaging-Design-using-Zemax
本项目区别于上一个光学设计初版，除了引入单透镜系统还引入双胶合透镜系统，利用Zemax构建数据据，根据控制变量法，改变焦距等物理量观察光斑变化，通过python提取像素重心与灰度计算RMS光斑大小

详细介绍：The main objective of this project is to combine optical simulation with machine learning to accelerate optical design and imaging quality prediction.

First, we built optical models of both single lenses and achromatic doublet lenses in Zemax. By varying parameters such as curvature radius, lens thickness, and image plane position, we generated simulation datasets with corresponding RMS spot sizes. The single-lens dataset contains 480 samples, while the doublet dataset contains 1,000 samples.

Next, we trained several machine learning regression models using Python and Scikit-learn, including Linear Regression, Ridge Regression, Random Forest, Gradient Boosting, Support Vector Regression, and K-Nearest Neighbors. The data were split into training and testing sets in an 8:2 ratio, standardized using StandardScaler, and optimized through 5-fold cross-validation.

To validate the model, we also built a real optical experimental platform using a laser, optical rail, lenses, and a CMOS camera. Spot images were processed with Python to calculate RMS spot radius, and the experimental results were compared with both Zemax simulations and machine learning predictions.

The results showed that the Gradient Boosting Regressor achieved the best performance for the single-lens system with an RMSE of 0.055 mm and an R² of 0.99. For the doublet system, both Gradient Boosting and Random Forest achieved an RMSE of 0.0053 mm with an R² of 0.98, demonstrating excellent prediction accuracy.

Finally, we developed a web-based platform where users can input lens parameters to predict imaging quality in real time or upload spot images for automatic analysis.
