import pandas as pd             
import numpy as np
import matplotlib.pyplot as plt

url = "https://drive.google.com/uc?export=download&id=17lJ-lhEI5v77hBkr97gzhTkxd7WKQPU6"

input_df = pd.read_excel(url, 0) 
#input_df.head()  
#input_df.tail() 
input_matrix = input_df.values 
fig, ax = plt.subplots(3, 1, figsize = (10, 8)) 
timestamps = range(0, input_matrix.shape[0]) 


begin = len(range(0, input_matrix.shape[0])) - 7*24 - 1 
end = len(range(0, input_matrix.shape[0])) 

ax[0].plot(timestamps[begin : end], input_matrix[begin : end, 0], '#AA11BB', marker = '.', linewidth = 1, markersize = 3) 
ax[1].plot(timestamps[begin : end], input_matrix[begin : end, 1], 'red', marker = '.', linewidth = 1, markersize = 3) 
ax[2].plot(timestamps[begin : end], input_matrix[begin : end, 2], 'green', marker = '.', linewidth = 1, markersize = 3) 

ax[0].set_ylabel('Фабрика_1') 
ax[1].set_ylabel('Фабрика_2') 
ax[2].set_ylabel('Разрез') 
ax[0].grid(True) 
ax[1].grid(True) 
ax[2].grid(True) 
ax[-1].set_xlabel('Время, час') 
plt.show()
