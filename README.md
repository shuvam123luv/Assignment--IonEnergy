#Correlation Result of a battery management system



The code is wriiten to find the correlation between variables of BMS installed in Telecom Tower. The techniques used are:- 
1)Spearman's Rank correlation
2)Pearson correlation 

Relationship between Grid status Vs SOC

Correlation_SOC_VS_Grid Status:
SpearmanrResult(correlation=0.16756363907401717, pvalue=1.2301165872017372e-194)
 
As per the result the variables are less correlated.

Relationship between Equivalent cycles  Vs SOH

SpearmanrResult(correlation=-0.9999891918148036, pvalue=0.0)
Pearson Coefficient: (-0.9842624478536393, 0.0)

As per the result the variables are very highly  negatively correlated. which means increase in a value of a variable causes decrease in other variable 
 Relation ship between Temperature  Vs SOC

Correlation Between SOC Vs Temperture:
Pearson Coefficient: (-0.36904035326610596, 0.0)
Spearman Coefficient: SpearmanrResult(correlation=-0.2066032952919746, pvalue=5.306806318224385e-297)
 
 
 As per the result the the the variables are moderately negatively correlated.
