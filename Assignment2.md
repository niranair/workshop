## <div align="center"> Using CDR and Mobile Phone Data in a Stacked Architecture Machine Learning Model to predict Malaria Dynamics in Nigeria

### **Introduction**

The purpose of this research is to develop the best machine learning method which utilizes spatial, demographic, environmental, and mobile phone data to predict malaria dynamics in Nigeria up to four weeks in the future so that resources can be distributed in a timely and efficient manner. Third world low income countries present the highest rates of infectious disease spread and this is because there is a lack of data surrounding individual human movement. Previously, during epidemics, countries have been unable to predict the magnitude of the outbreak and allocate resources in a timely manner [8]. 

### **Human Development Topic**

Malaria is a vector borne disease caused by the Plasmodium species. According to the CDC, over 3.2 billion people are at risk of malaria. In 2018 there were over 228 million cases worldwide, and of those cases 405,000 people died from the disease. Although malaria is a global problem, middle-to-high income countries have been able to abolish the disease for the most part, therefore most of the disease burden still lays on low-income countries, especially in sub-Saharan Africa. Of the 228 million cases worldwide, over 25% of them were in Nigeria —  the most populous country in Africa with over 190 million citizens. In Nigeria, 97% of its citizens are at risk of malaria. 

WHO has made great progress to eradicate the disease through its Global Technical Strategy for Malaria (2016 - 2030), its technical framework to control and eliminate the disease, but it is still not enough, but each year hundreds of thousands of people continue to die from this disease, even though it is controllable. With a methodology which predicts which areas will be future hotspots for the disease, aid can be distributed to control the disease in specific areas, before it takes over. 

The spread of malaria has become ever more complex as human interconnectedness has increased. Oftentimes asymptomatic people will travel and interact with other people, not knowing they have the disease. Malaria is also difficult to track because of the seasonality of the disease. To fully understand the spread of the disease it is essential to understand both mosquito and human population dynamics. 

Amartya Sen defines human development as the process of enlarging human opportunities. To expand human opportunity and potential, their situations must be removed from unfreedoms, including inadequate healthcare. In many low income regions, the people are not provided with adequate healthcare, either because the systems are not in place and they do not have the resources, or the resources are not being targeted in an accurate and timely manner. I will be focusing on the later, which involves predicting infectious disease dynamics so that resources may be effectively directed to those in need. By doing this, human development will progress because a major development unfreedom will be removed.

### **Methods** 

In the different papers, authors tested different machine learning models to predict disease dynamic locations. Using a disease prediction model is more beneficial than any statistical model because they can handle situations in real time, whereas statistical models have delays in reporting and do not improve overtime [2]. 

The most common model used is the ARIMA model which is an Auto Regressive Integrated Moving Average Model which is used to forecast future time points. AutoRegression calculates the weights for a variable based on past values of itself. The ARIMA model looks at trends between previous time points of itself and predicts future time points from the previous trends [9]. The ARIMA is the most commonly used model because it accounts for the seasonality and transmissibility better than most models. Although, ARIMA models are limited by the assumption that there is a linear correlation structure [7].

Chae, Sangwon & Kwon, Sungjun & Lee, Donghyun compare ARIMA model to the OLS (Ordinary Least Squares) model to ten different LSTM (Long-Short Term Memory) models and ten different DNN (Deep Neural Network) models. to build the machine learning models. The conclusions showed that the DNN performed the most stably with a 24% performance improvement over the ARIMA model. The LSTM also did much better than the traditional ARIMA model with a 19% performance improvement. The DNN models performed best on average, but the LSTMs proved to be more accurate when infectious diseases were spreading. 

Deep learning neural networks are a more advanced version of neural networks because they contain many hidden layers, whereas neural networks only contain one, along with the input and output layer. LSTMs are a more advanced subset of RNNs (Recurrent Neural Networks). Recurrent Neural Networks are generally used for sequential data. The most common uses for RNNs are making predictions within text, but in this case, the RNN is being used to make predictions over space and time. One pitfall of RNNs is their inability to maintain information/context over time, and that’s why LSTMs are being used instead. LSTMs contain a forget gate layer which either outputs a 0 or 1 after each iteration which is used to represent which information should be kept for context in the future and which information should be forgotten. LSTMs prevent gradient loss over time which is useful for this situation where context and information must be maintained over longer periods of time. [2]

In the paper, A novel model for malaria prediction based on ensemble algorithms, the authors discuss the ARIMA, STL_ARIMA, BP-ANN, and LSTM machine learning models as methods for predicting disease dynamics. The individual performance of the models were measured using the root mean squared error (RMSE), mean absolute squared error (MASE), and mean absolute deviation (MAD). The RSME of the four models were 13.176, 14.543, 9.571 and 7.208, the MASE values were 0.469, 0.472, 0.296 and 0.266, and the MAD values were 6.403, 7.658, 5.871 and 5.691. The authors argued that although the models were able to perform decently, no one model can capture all of the properties of the data structure. Using gradient-boosting regression trees, the models can be combined to form a single stacking architecture model which combines all of the distinct algorithms of the individual models to create a more robust and high-performing model. When the performance of the stacked model was evaluated, every performance metric value decreased. The RSME, MASE, and MAD values were 6.810, 0.224 and 4.62 respectively —  meaning that the stacked architecture model performed more accurately than any of the previously tested individual models [7]. In this paper, I proposed using the stacked structure model to combine the ARIMA, LSTM, and DNN learning models discussed above.

In the paper,  A dynamic neural network model for predicting risk of Zika in real time, the authors discuss using a dynamic neural network in which three parameters can be changed by the user, the indicators, the risk classification scheme, and prediction window. Using a dynamic stacked structure model will ensure not only that the model is accurate, but also that it is adaptable and customizable for individual situations [8].

### Data

Throughout all the papers the authors use different combinations of weather, rainfall, humidity, temperature, elevation, topographic wetness, vegetation, land cover, distance to water, infrastructure, travel, socioeconomic, and population data as prediction indicators for the different machine learning models [2,4]. To choose the most statistically significant covariates, I suggest a feature selection method which utilizes a random forest regression model. Random forest consists of hundreds of decision trees which do not see all of the other features and observations which makes sure that thre trees are de-correlated. Since the trees are de-correlated, this prevents overfitting of the model [10].

Previously accurate big data on human movement did not exist in low-income countries and prediction models and maps were based on simplistic assumptions about human movement and interactions. Human movement information was based on census data, household surveys, traffic and road network data, and small GPS studies. Currently, 39% of the population in Sub-Saharan Africa owns a mobile phone, and this number is increasing rapidly. With the rise of mobile phone technology, CDR data has made tracking human movement in real time possible [1,6]. 

CDR data is created every time a phone is used to make or receive a call or text. When the phone is used a digital data point is logged that registers the SIM card and cell tower. Will millions of text and calls made everyday, CDR data has emerged as a form of big data [6]. 

Before CDR data, human movement was measured by traffic and road network data, but with constant and real-time data accessible by mobile phones, CDR data can be used to replace or supplement the other covariates used for predicting malaria dynamics. The study done in Assessing the interplay between human mobility and mosquito borne diseases in urban environments, showed that there is a significant correlation between human movement and mobile phone data [3]. 

When analysing CDR data, not all of the data is significant and should be used. The data should be filtered to look at three types of human movement: individuals in low risk areas traveling to high risk areas, individuals in high risk areas travelling to low risk areas, and people in different endemic regions meeting and bringing together different populations of parasites that would otherwise be distinct.

One difficulty that CDR data poses is the lack of openly available data because companies do not want to give up their information easily because they have to take into account privacy concerns. To remedy this issue, much of the CDR data being used is anonymous so that the information cannot be tracked back to specific individuals. Another difficulty is with biases in terms of who owns phones, the calling behavior of individuals, tower density within a specific area, and how many SIM cards individuals own. Although the data is not perfect, currently, it is the best way to model human movement both quickly and accurately. Mobile phone data has the power to quantify human movements and relate these population dynamics to the spread of infectious diseases in third-world countries where disease epidemics are high, and available data is low. [1]

### Discussion

Modeling the spread of a vector borne disease such as malaria is difficult because many different factors including human population, socioeconomic factors, environmental factors, and especially human movement affect the spread of the disease. Countries in sub-saharan Africa carry the burden of the disease because they have been unable to properly control and eradicate the disease due to a lack of resources. In this paper I propose using a flexible stacked architecture machine learning model composed of the commonly used ARIMA model, and newer LSTM and DNN learning models to predict hotspots for the disease and where the disease will most likely spread in the future. Understanding human mobility is essential to understand how the disease will spread, and that is why I propose using CDR and mobile phone data as the primate feature indicator of human movement used in the prediction model along with the other statistically significant environmental and population covariates previously used. 

### Sources 

[1] Wesolowski Amy, Buckee Caroline O., Engø-Monsen Kenth, Metcalf C. J. E. Connecting Mobility to Infectious Diseases: The Promise and Limits of Mobile Phone Data. Journal of Infectious Diseases. 2016;214(suppl 4):S414–S420. doi: 10.1093/infdis/jiw273.

[2] Chae, Sangwon & Kwon, Sungjun & Lee, Donghyun. (2018). Predicting Infectious Disease Using Deep Learning and Big Data. International Journal of Environmental Research and Public Health. 15. 1596. 10.3390/ijerph15081596.

[3] Massaro, E., Kondor, D. & Ratti, C. Assessing the interplay between human mobility and mosquito borne diseases in urban environments. Sci Rep 9, 16911 (2019). https://doi.org/10.1038/s41598-019-53127-z

[4] Tatem AJ, Huang Z, Narib C, Kumar U, Kandula D, Pindolia DK, et al. Integrating rapid risk mapping and mobile phone call record data for strategic malaria elimination planning. Malar J. 2014;13:52. doi: 10.1186/1475-2875-13-52.

[5] Gupta Abhijit. (2019). Prediction of epidemic disease dynamics using machine learning. Medium.

[6] Buckee CO, Wesolowski A, Eagle NN, Hansen E, Snow RW. Mobile phones and malaria: modeling human and parasite travel. Travel Med. Infect. Dis. 2013;11:15–22. doi: 10.1016/j.tmaid.2012.12.003.

[7] Wang, M., Wang, H., Wang, J., Liu, H., Lu, R., Duan, T., Gong, X., Feng, S., Liu, Y., Cui, Z., Li, C., & Ma, J. (2019). A novel model for malaria prediction based on ensemble algorithms. PloS one, 14(12), e0226910. https://doi.org/10.1371/journal.pone.0226910

[8] Akhtar, M., Kraemer, M.U.G. & Gardner, L.M. A dynamic neural network model for predicting risk of Zika in real time. BMC Med 17, 171 (2019). https://doi.org/10.1186/s12916-019-1389-3

[9] Malik, F. (2018, October 2). Understanding Auto Regressive Moving Average Model - ARIMA. Retrieved from https://medium.com/fintechexplained/understanding-auto-regressive-model-arima-4bd463b7a1bb

[10] Dubey, A. (2018, December 15). Feature Selection Using Random forest. Retrieved from https://towardsdatascience.com/feature-selection-using-random-forest-26d7b747597f


