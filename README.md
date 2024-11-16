As modern technology and business increasingly adopt an IoT (Internet of Things) approach, the reliance on global connectivity becomes paramount. Satellites play a critical role in this for worldwide internet coverage. Although internet satellites such as Starlink account for around 4000 satellites, other uses such as Earth Monitoring, GPS and National Defence bring the total number of satellites to over 7000, with ever more expected in coming years. The management of these numbers of satellites becomes increasingly problematic, not only to avoid collisions and damage to these satellites, but also to monitor for adversarial actions. This monitoring requires satellite manoeuvre detection algorithms, both to avoid collisions and detect unlogged manoeuvres. 

This study evaluates the performance of Arima and XGBoost models for anomaly detection in Brouwer Mean Motion data across five satellites: CryoSat-2, Jason-1, Sentinel-3A, Fengyun-2F, and Haiyang-2A. Each satellite represents unique characteristics, such as varying noise levels, cyclical relationships, and response rates to manoeuvres. The incorporation of Normalized Residuals significantly improved anomaly detection accuracy, particularly in datasets with high noise levels, underscoring their value in enhancing model performance. The findings suggest that ARIMA, combined with Normalized Residuals, provides a robust and reliable approach to anomaly detection in satellite data, effectively addressing the challenges of modern satellite monitoring.


To aid in navigating the code the contents/numbering are as follows:

1. Satellite position anomaly detection
	1.1 Code Setup
	1.2 Define Functions
2. Model CryoSat-2
	2.1 Import Data
	2.2. Exploratory Data Analysis
	2.3 Prepare individual dataframes per element
	2.4 ARIMA Model
		2.4.1 Propagate elements
		2.4.2 Highlight Anomalies
			2.4.2.1 Brouwer Mean Motion Anomaly Detection
				2.4.2.1.1 Fixed threshold
 				2.4.2.1.2 Moving Average threshold
			2.4.2.2 Eccentricity Anomaly Detection
 				2.4.2.2.1 Fixed threshold
				2.4.2.2.2 Moving Average threshold
			2.4.2.3 Argument of Perigee Anomaly Detection
				2.4.2.3.1 Fixed threshold
 				2.4.2.2.2 Moving Average threshold
			2.4.2.4 Mean Anomaly Anomaly Detection
				2.4.2.4.1  Fixed threshold
				2.4.2.4.2 Moving Average threshold
			2.4.2.5 Inclination Anomaly Detection
 				2.4.2.5.1 Fixed threshold
				2.4.2.5.2 Moving Average threshold
			2.4.2.6 Right Ascension Anomaly Detection
				2.4.2.6.1 Fixed threshold
 				2.4.2.6.2 Moving Average threshold
 		2.4.3 Tune for Brouwer Mean Motion
		2.4.4 Propagate elements for tuned Model
		2.4.5 Highlight Anomalies for tuned Model
 			2.4.5.1 Fixed threshold
			2.4.5.2 Moving Average threshold
			2.4.5.3 Moving Average threshold New
 	2.5 Gradient Booster Model
 		2.5.1 Propagate elements
		2.5.2 Tune
		2.5.3 Propagate elements for tuned Model
 		2.5.4 Highlight Anomalies for tuned Model
 			2.5.4.1 Fixed threshold
 				2.5.4.1.1 Train
 				2.5.4.1.2 Test
 			2.5.4.2 Moving Average threshold
 			2.5.4.3 Moving Average threshold New
 	2.6 Model Comparison
 3. Model Jason 1
	3.1 Import Data
	3.2 Prepare individual dataframes per element
 	3.3 ARIMA Model
 		3.3.1 Propagate elements
		3.3.2 Tune
 		3.3.3 Propagate elements for tuned Model
 		3.3.4 Highlight Anomalies for tuned Model
 			3.3.4.1 Fixed threshold
 			3.3.4.2 Moving Average threshold
			3.3.4.3 Moving Average threshold New
 	3.4 Gradient Booster Model
		3.4.1 Propagate elements
		3.4.2 Tune
 		3.4.3 Propagate elements for tuned Model
 		3.4.4 Highlight Anomalies for tuned Model
			3.4.4.1 Fixed threshold
				3.4.4.1.1 Train
 				3.6.4.1.2 Test
			3.4.4.2 Moving Average threshold
			3.4.4.3 Moving Average threshold New
 	3.5 Model Comparison
 4. Model Sentinel 3A
 	4.1 Import Data
 	4.2 Prepare individual dataframes per element
 	4.3 ARIMA Model
 		4.3.1 Propagate elements
		4.3.2 Tune
		4.3.3 Propagate elements for tuned Model
		4.3.4 Highlight Anomalies for tuned Model
			4.3.4.1 Fixed threshold
 			4.3.4.2 Moving Average threshold
			4.3.4.3 Moving Average threshold New
	4.4 Gradient Booster Model
		4.4.1 Propagate elements
		4.4.2 Tune
 		4.4.3 Propagate elements for tuned Model
 		4.4.4 Highlight Anomalies for tuned Model
 			4.4.4.1 Fixed threshold
 				4.4.4.1.1 Train
				4.4.4.1.2 Test
 			4.4.4.2 Moving Average threshold
 			4.4.4.3 Moving Average threshold New
 	4.5 Model Comparison
 5. Model Fengyun 2F
	5.1 Import Data
 	5.2 Prepare individual dataframes per element
 	5.3 ARIMA Model
 		5.3.1 Propagate elements
		5.3.2 Tune
		5.3.3 Propagate elements for tuned Model
 		5.3.4 Highlight Anomalies for tuned Model
 			5.3.4.1 Fixed threshold
			5.3.4.2 Moving Average threshold
			5.3.4.3 Moving Average threshold New
	5.4 Gradient Booster Model
 		5.4.1 Propagate elements
 		5.4.2 Tune
 		5.4.3 Propagate elements for tuned Model
		5.4.4 Highlight Anomalies for tuned Model
 			5.4.4.1 Fixed threshold
				5.4.4.1.1 Train
				5.4.4.1.2 Test
 			5.4.4.2 Moving Average threshold
			5.4.4.3 Moving Average threshold New
	5.5 Model Comparison
 6. Model Haiyang 2A
 	6.1 Import Data
 	6.2 Prepare individual dataframes per element
 	6.3 ARIMA
 		6.3.1 Propagate elements
 		6.3.2 Tune
		6.3.3 Propagate elements for tuned Model
		6.3.4 Highlight Anomalies for tuned Model
 			6.3.4.1 Fixed threshold
 			6.3.4.2 Moving Average threshold
 			6.3.4.3 Moving Average threshold New
	6.4 Gradient Booster Model
 		6.4.1 Propagate elements
		6.4.2 Tune
 		6.4.3 Propagate elements for tuned Model
 		6.4.4 Highlight Anomalies for tuned Model
			6.4.4.1 Fixed threshold
				6.4.4.1.1 Train
				6.4.4.1.2 Test
			6.4.4.2 Moving Average threshold
 			6.4.4.3 Moving Average threshold New
	6.5 Model Comparison


Appendix - Data Dump
