## Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
 



### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.

### PROGRAM:
```
DEVELOPED BY: LOKESH R
REG NO: 212222240055
```


```
from pandas import read_csv
from pandas import datetime
from matplotlib import pyplot
from pandas.plotting import autocorrelation_plot
from pandas import DataFrame
from statsmodels.tsa.arima_model import ARIMA
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
from statsmodels.tsa.arima_process import ArmaProcess
import matplotlib.pyplot as plt
import numpy as np
import warnings
warnings.filterwarnings('ignore')
import matplotlib.pyplot as plt
import numpy as np
```
```
plt.rcParams['figure.figsize'] = [10, 7.5]
```
```
ar1 = np.array([1,0.33])
ma1 = np.array([1,0.9])
ARMA_1 = ArmaProcess(ar1,ma1).generate_sample(nsample = 1000)
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_1)
plot_pacf(ARMA_1)
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=10000)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
```
OUTPUT:
SIMULATED ARMA(1,1) PROCESS:


![313937049-0db69bc4-9cb4-4e67-9c73-cc35a59ddedd](https://github.com/LokeshRajamani/TSA_EXP4/assets/120544804/2e28afb3-1177-4d6c-921d-2bed3a681eb3)



Partial Autocorrelation:


![313937422-daaf27b7-6430-4163-b781-25a692adbd8b](https://github.com/LokeshRajamani/TSA_EXP4/assets/120544804/9af08292-f42a-4b22-84fa-a685a087d73c)



Autocorrelation:


![313937116-14dd69f9-5ec9-4c25-8820-ff927778f48f](https://github.com/LokeshRajamani/TSA_EXP4/assets/120544804/bdd46da9-8e91-424f-aafa-02ab03378e43)



SIMULATED ARMA(2,2) PROCESS:


![313937186-57c65607-9103-426f-b271-9b6497c9df44](https://github.com/LokeshRajamani/TSA_EXP4/assets/120544804/a7c2ca06-1618-4db7-911c-d58bad337790)



Partial Autocorrelation:


![313937422-daaf27b7-6430-4163-b781-25a692adbd8b](https://github.com/LokeshRajamani/TSA_EXP4/assets/120544804/ac1ac50c-3e69-45df-97fa-001e1752a787)


Autocorrelation:


![313937253-5d9d0057-4881-4f44-900d-b912fe72891c](https://github.com/LokeshRajamani/TSA_EXP4/assets/120544804/ed57027b-417b-4c55-b311-2a045cf2af18)


RESULT:
Thus, a python program is created to fir ARMA Model successfully.
