# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 16:08:24

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
## Regular Differencing
```
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
data.head()
passengers['shifted_value']=passengers['#Passengers'].shift(1)
passengers['difference_value']=passengers['#Passengers']-passengers['shifted_value']
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```

## Seasonal Adjustment
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
passengers=pd.DataFrame(data)
result=seasonal_decompose(passengers['#Passengers'],model='additive',period=1)
seasonal=result.seasonal
passengers['Seasonal_value']=passengers['#Passengers']-seasonal
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```
## Log Transformation
```
import numpy as np
import pandas as pd
data= pd.read_csv('AirPassengers.csv')
data.head()
data.dropna(inplace=True)
x=data['Month']
y=data['#Passengers']
data_log=np.log(data['#Passengers'])
X=data['Month']
Y=data_log
import matplotlib.pyplot as plt
plt.plot(x,y)
plt.xlabel('Original Data')
plt.plot(X,Y)
plt.xlabel('Log- Transformed data')
```

### OUTPUT:

REGULAR DIFFERENCING:


![WhatsApp Image 2024-04-06 at 13 37 46_6bc2c8be](https://github.com/Hanumanth26/TSA_EXP1B/assets/121033192/02576369-90a5-429c-8f69-91d94739321b)


SEASONAL ADJUSTMENT:

![WhatsApp Image 2024-04-06 at 13 37 46_001d0334](https://github.com/Hanumanth26/TSA_EXP1B/assets/121033192/789e8672-8f87-4c0d-8257-06abcbee1eba)


LOG TRANSFORMATION:

![WhatsApp Image 2024-04-06 at 13 37 46_bf5d6df3](https://github.com/Hanumanth26/TSA_EXP1B/assets/121033192/66fd5bfb-9096-4200-973e-313d4c617c88)




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
