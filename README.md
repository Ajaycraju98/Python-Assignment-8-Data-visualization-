# Python-Assignment-8-Data-visualization-
This  Assignment explains about the Data Visualization in Python
# to deactivate warnings
import warnings
import sys
if not sys.warnoptions:
    warnings.simplefilter("ignore")
# Exercise 1: Create a line plot using matplotlib pyplot that displays the population of four different cities over time. 
Each city should have its own line, and the x-axis should represent years (e.g. 2010, 2011, 2012, etc.) while the y-axis should represent the population. 
The data for the four cities is provided below: 
City A: [500000, 550000, 600000, 650000, 700000, 750000, 800000] 
City B: [800000, 850000, 900000, 950000, 1000000, 1050000, 1100000] 
City C: [1000000, 1050000, 1100000, 1150000, 1200000, 1250000, 1300000] 
City D: [1200000, 1250000, 1300000, 1350000, 1400000, 1450000, 1500000] 

import matplotlib
from matplotlib import pyplot as plt

# x axis values
x = [2010,2011,2012,2013,2014,2015,2016]
# Y-axis values
y1 = [500000, 550000, 600000, 650000, 700000, 750000, 800000]  # City A
y2 = [800000, 850000, 900000, 950000, 1000000, 1050000, 1100000]  # City B
y3 = [1000000, 1050000, 1100000, 1150000, 1200000, 1250000, 1300000]  # City C
y4 = [1200000, 1250000, 1300000, 1350000, 1400000, 1450000, 1500000]  # City D


plt.plot(x,y1,'b', label="city A ",linewidth=2, marker='.', linestyle='solid', markersize=10, color='blue')
plt.plot(x,y2,'b', label="city B",linewidth=2, marker='.', linestyle='solid', markersize=10, color='red')
plt.plot(x,y3,'b', label="city C",linewidth=2, marker='.', linestyle='solid', markersize=10, color='green')
plt.plot(x,y4,'b',label="city D",linewidth=2, marker='.', linestyle='solid', markersize=10, color='orange')

plt.xlabel('Years',fontsize=12)
plt.ylabel('Population',fontsize=12)
plt.title('Population of four different cities over time',fontsize=14)


# X, Y axis Tickmarks (scale of your graph)
plt.xticks([2010,2011,2012,2013,2014,2015,2016])
plt.yticks([200000, 400000, 600000, 800000, 1000000, 1200000, 1400000, 1600000], 
           labels=['200K', '400K', '600K', '800K', '1M', '1.2M', '1.4M', '1.6M'])


# Add a Legend
plt.legend() 
# function to show the plot
plt.show()

# Exercise 2: Create a scatter plot using seaborn that shows the relationship between the number of hours studied and the test scores obtained by a group of students.
Use the following data: Hours Studied: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] 
Test Scores: [93, 57, 61, 54, 51, 53, 87, 81, 83, 85] 

import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

hours_studied=[1, 2, 3, 4, 5, 6, 7, 8, 9, 10] 
test_scores=[93, 57, 61, 54, 51, 53, 87, 81, 83, 85] 

df = pd.DataFrame({'Hours Studied': hours_studied, 'Test Scores': test_scores})

# Creating the scatter plot
sns.scatterplot(x='Hours Studied', y='Test Scores', data=df, color='b', s=100, edgecolor='black')

# Add labels and title
sns.set_style("dark")
plt.xlabel("Test Scores",fontsize=12,)
plt.ylabel("Hours Studied",fontsize=12)
plt.title("Relationship Between Hours Studied and Test Scores", fontsize=14)
plt.figure(figsize=(8, 6))
# Show plot
plt.show()

# Exercise 3: Create a bar chart using matplotlib pyplot that shows the total sales for each month of the year. 
Use the following data: Month: ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"] 
Sales: [11860, 10480, 4997, 5523, 13965, 6011, 13158, 9533, 5158, 9058, 11346, 6675]

# Data for the bar chart
Month = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"] 
Sales = [11860, 10480, 4997, 5523, 13965, 6011, 13158, 9533, 5158, 9058, 11346, 6675]

# Create the bar chart with data labels
plt.bar(Month,Sales,color='red')

# Add data labels
for i, S in enumerate(Sales):
    plt.text(i, S + 1 , str(S), ha='center')

# Add labels and title
plt.xlabel('Month',fontsize=12)
plt.ylabel('Sales',fontsize=12)
plt.title('Total sales for each month of the year',fontsize=14)

plt.figure(figsize=(10, 10))

# Display the bar chart
plt.show()
