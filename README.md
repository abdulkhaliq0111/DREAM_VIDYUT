# DREAM_VIDYUT


1.  Introduction

	a. Overview
  
	b. Scope
  
2.   Preliminary Analysis:

	a. Qualitative Analysis
  
	b. Quantitative Analysis
  
	c. Data Pre-processing 
  
3.   Model Selection

4.   Parameter Tuning

5.   Results

6.   Insights

7.   Appendix


# Overview:

Dream Vidyut, hereinafter referred to as the company plans to predict power consumption of five different corporate buildings measured across three electricity meters namely Main Meter, Sub-Meter 1 and Sub-Meter 2 respectively to further their goals of increasing sustainability.
Available Data : Power consumption in 2017 ( April-Dec )
 
Deliverable : Power consumption in 2018 ( Jan- 18th April )

Scope :
 
Electricity demand (power consumption)  prediction plays an essential role in short-term load allocation and long-term planning for new generation and transmission infrastructures. An accurate prediction also allows to take better decisions in terms of cost and energy efficiency.
It prepares the electricity companies to provide the unbreakable power supply to the consumers and also help them to manage and prepare there resources accordingly.
Using the power consumption prediction companies can also predict their future economic state and than plan accordingly to maximize there profit as well as  can improve there economic state.

# Preliminary Qualitative Analysis:
Daily Pattern  : 
It was assumed that certain seasonality should emerge daily because of similarity between various work days. It was quantified later on to validate this hypothesis.

Variations among buildings:
Separate trends might have emerged for different buildings. Hence, exhaustive analysis was needed to capture unique patterns across the buildings.


Multiple Seasonality:
Power consumption might have possible multiple seasonality - (Daily, weekly, monthly and yearly). Thus, models robust enough to capture multiple seasonality should be given preference.


# Preliminary Quantitative Analysis & Data Preprocessing:

Initially characteristic features of given data such as trend and seasonality were visualized to determine whether given data is stationary. Time series models have different approaches for stationary and non-stationary data, thus it becomes deterministic for model selection and further approach.
Separate decomposition for all the buildings were generated to modify the model used accordingly.


It was observed that across the buildings there was no strong upward trend. Weekly and Daily seasonality were detected as expected.


# Building wise analysis : 
Insight 1: It was observed that Building 1 had higher peaks towards the last months while the rest had minor variations with peaks somewhere in the middle of the year.


Insight 2 : A particular company operates for certain work hours every day, thus there should be peaks for certain time.
Keeping that in hindsight, mean of power consumption was plotted for every day with reference to particular time.


# Data Pre-processing

Seasonality was removed from the dataset using  differencing for the period observed earlier .

# Model selection

Hypothesis: With multiple seasonality (Daily and Weekly) a model with a high inclination towards detecting sequences and longer memory should be used. That’s why LSTM was selected for the given dataset.

Comparison:

ARMAs and ARIMAs are particularly simple models which are essentially linear update models plus some noise thrown in. With nonlinear activation functions, neural networks are approximations to nonlinear functions. RNNs and LSTMs are thus essentially a nonlinear timeseries model, where the nonlinearity is learned from the data. These will not do well with small amounts of data because it needs to learn the nonlinearity, and training times will be much longer than finding ARMA/ARIMA coefficients. However, with enough data you'll get an RNN or LSTM which matches the nonlinearities of your real data well, which in tern makes its predictions much more accurate than the ARMA/ARIMA
LSTM models are powerful enough to learn the most important past behaviors and understand whether or not those past behaviors are important features in making future predictions. 



