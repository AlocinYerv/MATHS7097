As modern technology and business increasingly adopt a global approach, the reliance on satellites for worldwide coverage has become more critical. 
Currently this global coverage is mostly achieved with the use of satellites, with the number of satellites set to increase even more from the current level of roughly 7000. 
The management of these numbers of satellites becomes increasingly problematic, not only to avoid collisions and damage to these satellites, but also to monitor for adversarial actions. 
This monitoring requires satellite manoeuvre detection algorithms, both to avoid collisions and detect unlogged manoeuvres. 
This project employs an Arima model to predict satellite position and from there identify manoeuvres.

The contents/numbering of the code is as follows:

1.	Satellite position anomaly detection
1.1	Code Setup
1.2	Define Functions
2.	Model CryoSat-2
2.1	Import Data
2.2	Exploratory Data Analysis
2.3	Prepare individual dataframes per element
2.4	Test if Individual elements are stationary and determine rough p,d,q values
2.4.1	Test Brouwer mean motion
2.4.1.1	Test Stationarity
2.4.1.2	Determine Difference (d)
2.4.1.3	Determine Regression order (p)
2.4.1.4	Determine Residual order (q)
2.4.2	Test Eccentricity
2.4.2.1	Test Stationarity
2.4.2.2	Determine Difference (d)
2.4.2.3	Determine Regression order (p)
2.4.2.4	Determine Residual order (q)
2.4.3	Test Argument of Perigee
2.4.3.1	Test Stationarity
2.4.3.2	Determine Difference (d)
2.4.3.3	Determine Regression order (p)
2.4.3.4	Determine Residual order (q)
2.4.4	Test Mean Anomaly
2.4.4.1	Test Stationarity
2.4.4.2	Determine Difference (d)
2.4.4.3	Determine Regression order (p)
2.4.4.4	Determine Residual order (q)
2.4.5	Test Inclination
2.4.5.1	Test Stationarity
2.4.5.2	Determine Difference (d)
2.4.5.3	Determine Regression order (p)
2.4.5.4	Determine Residual order (q)
2.4.6	Test Right Ascension
2.4.6.1	Test Stationarity
2.4.6.2	Determine Difference (d)
2.4.6.3	Determine Regression order (p)
2.4.6.4	Determine Residual order (q)
2.5	Propagate elements
2.6	Highlight Anomalies
2.6.1	Brouwer Mean Motion Anomaly Detection
2.6.2	Eccentricity Anomaly Detection
2.6.3	Argument of Perigee Anomaly Detection
2.6.4	Mean Anomaly Anomaly Detection
2.6.5	Inclination Anomaly Detection
2.6.6	Right Ascension Anomaly Detection
2.7	Find optimal p,d,q for Brouwer Mean Motion
2.8	Propagate elements for best p,d,q
2.9	Highlight Anomalies for best p,d,q
3.	Model Jason 1
3.1	Import Data
3.2	Prepare individual dataframes per element
3.3	Propagate elements
3.4	Find optimal p,d,q for Brouwer Mean Motion
3.5	Propagate elements for best p,d,q
3.6	Highlight Anomalies for best p,d,q
4.	Model Sentinel 3A
4.1	Import Data
4.2	Prepare individual dataframes per element
4.3	Propagate elements
4.4	Find optimal p,d,q for Brouwer Mean Motion
4.5	Propagate elements for best p,d,q
4.6	Highlight Anomalies for best p,d,q
5.	Model Fengyun 2F
5.1	Import Data
5.2	Prepare individual dataframes per element
5.3	Propagate elements
5.4	Find optimal p,d,q for Brouwer Mean Motion
5.5	Propagate elements for best p,d,q
5.6	Highlight Anomalies for best p,d,q
6.	Model Haiyang 2A
6.1	Import Data
6.2	Prepare individual dataframes per element
6.3	Propagate elements
6.4	Find optimal p,d,q for Brouwer Mean Motion
6.5	Propagate elements for best p,d,q
6.6	Highlight Anomalies for best p,d,q
Appendix - Data Dump
