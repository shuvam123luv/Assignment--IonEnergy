# Assignment--IonEnergy

# Importing Libraries 

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
from matplotlib import rcParams
from matplotlib.cm import rainbow
from scipy.stats import pearsonr , spearmanr

# Loading dataset
assignment=pd.read_csv("Assignment file for Data Analyst - assignment file.csv")
data=assignment.loc[:,["SOC","Equivalent cycle","SOH","Temperature"]]

# Plotting Correlation Matrix
corrmat=  data.corr()
f,ax=plt.subplots(figsize=(9,8))
sns.heatmap(corrmat, annot=True, ax=ax,cmap='autumn')
plt.title("Correlation Matrix")

plt.savefig('Correlation Matrix.jpg')

# Finding Correlation between SOH_VS_Equivalent_Cycles


fig= plt.figure(figsize=(10,10))

ax=fig.add_subplot(1,1,1)

ax.scatter("SOH", "Equivalent cycle", data=assignment, c="b",s=100)

ax.set_xlabel('SOH')
ax.set_ylabel('Equivalent cycle')
ax.set_title('Equivalent cycle Vs SOH')
plt.grid(color='r', linestyle='-', linewidth=0.9)

Correlation_SOC_VS_Equivalentcycle= spearmanr(assignment['SOH'],assignment['Equivalent cycle'])
print("Correlation_SOH_VS_Equivalentcycle: \n" ,Correlation_SOC_VS_Equivalentcycle)

Pearson1=pearsonr(assignment['SOH'],assignment['Equivalent cycle'])
print('Pearson Coefficient:',Pearson1)

plt.savefig('SOH_Vs_Equivalentcycle.jpg')

# Finding Correlation between SOC_VS_Temperature

fig= plt.figure(figsize=(10,10))

ax=fig.add_subplot(1,1,1)

ax.scatter("Temperature", "SOC", data=assignment, c="b",s=100)
plt.grid(color='r', linestyle='-', linewidth=0.9)

ax.set_xlabel('Temperature')
ax.set_ylabel('SOC')
ax.set_title('SOC Vs Temperature')

Pearson1=pearsonr(assignment['Temperature'],assignment['SOC'])

print("Correlation Between SOC Vs Temperture:")
print('Pearson Coefficient:\n ',Pearson1)

Spearman_Corr_Coeff= spearmanr(assignment[['Temperature']],assignment[['SOC']])
print("Spearman Coefficient: \n",Spearman_Corr_Coeff)

plt.savefig('Temperature_Vs_SOC.jpg')


# Finding Correlation between SOC_VS_Grid Status

fig= plt.figure(figsize=(10,10))

ax=fig.add_subplot(1,1,1)

ax.scatter("Grid status", "SOC", data=assignment, c="b",s=100)
plt.grid(color='r', linestyle='-', linewidth=0.9)

ax.set_xlabel('Grid Status')
ax.set_ylabel('SOC')
ax.set_title('SOC  Vs Grid status')

Correlation_SOC_VS_Temperature= spearmanr(assignment['Grid status'],assignment['SOC'])
print("Correlation_SOC_VS_Grid Status:\n" ,Correlation_SOC_VS_Temperature)

plt.savefig('SOC_Vs_GridStatus.jpg')


# Exploratory data analysis of SOC VS Grid Status.

sns.relplot(x="Grid status", y="SOC", data=assignment, hue="Current")


sns.relplot(x="Grid status", y="SOC", data=assignment, hue="Timestamp")

sns.relplot(x="Grid status", y="SOC", data=assignment, hue="Grid cumulative energy consumption")

# Exploratory data analysis of Equivalent cycle VS SOH.
sns.relplot(x="Equivalent cycle", y="SOH", data=assignment,hue="Current",height=7)
sns.relplot(x="Equivalent cycle", y="SOH",  data=assignment,hue="Total voltage",height=7)
sns.relplot(x="Equivalent cycle", y="SOH", data=assignment,hue="Grid power",height=7)

# Exploratory data analysis of SOC VS Temperature.
 
sns.relplot(x="SOC", y="Temperature", data=assignment,hue="Current",height=7)
sns.relplot(x="SOC", y="Temperature", data=assignment,hue="Total voltage",height=7)
sns.relplot(x="SOC", y="Temperature", data=assignment,hue="Grid power",height=7)


# Refrence of Concept used in finding the correlation

from IPython.display import IFrame 
Pearson= IFrame(src="https://en.wikipedia.org/wiki/Pearson_correlation_coefficient", width=1000, height=5000)
display(wiki)

# Refrence of Concept used in finding the correlation
from IPython.display import IFrame 
Spearman= IFrame(src="https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient", width=1000, height=5000)
display(Spearman)
