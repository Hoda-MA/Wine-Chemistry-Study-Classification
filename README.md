# Wines-Chemistry-Study
Wine is one the most popular beverage in the world. Flavonoids include the anthocyanins and tannins which contribute to the color and mouthfeel of the wine. Many people believe that red wine comes from red grapes and white wine comes from white grapes, While this is usually the case, it is for a different reason than most would assume.

In this study, I am aimed to understand the chemistry of wine and share the result with you. For getting more familiar with the chemistry of wine, you may take a look on its pH-values. moreover, the properties of wine is dependent on the ingredients hence the pH.



![Wine_pH_scale](https://user-images.githubusercontent.com/64262003/113576525-014ee680-9620-11eb-9e43-5a94bf3fe52c.png)

# Drawing the wine molecule!
<img width="425" alt="Flavonoid" src="https://user-images.githubusercontent.com/64262003/113578025-78857a00-9622-11eb-838b-988412461778.png">


<img width="830" alt="Untitled" src="https://user-images.githubusercontent.com/64262003/113577459-97374100-9621-11eb-88a5-6135e913cd82.png">


# checking out the null values:
wine.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 178 entries, 0 to 177
Data columns (total 14 columns):
Class                           178 non-null int64
Alcohol                         178 non-null float64
Malic acid                      178 non-null float64
Ash                             178 non-null float64
Alcalinity of ash               178 non-null float64
Magnesium                       178 non-null int64
Total phenols                   178 non-null float64
Flavanoids                      178 non-null float64
Nonflavanoid phenols            178 non-null float64
Proanthocyanins                 178 non-null float64
Color intensity                 178 non-null float64
Hue                             178 non-null float64
OD280/OD315 of diluted wines    178 non-null float64
Proline                         178 non-null int64
dtypes: float64(11), int64(3)
memory usage: 19.6 KB

# checking the distribution of wine classes in the table
histo=list(wine.columns)
for i in range(len(histo)):
    fig=wine.iloc[:,i].plot('hist', color='green', bins=50, figsize=(10,8))
    plt.title(wine.columns[i])
    
# ckecking the correlation between columns. I prefer personally the heat-map for doing this.
#correlational heat map
wine_corr=wine.iloc[:,:].corr();
plt.figure(figsize=(12,6))
sns.heatmap(wine_corr, cmap='YlGnBu', annot=True)
    plt.show()
    
![download](https://user-images.githubusercontent.com/64262003/113577826-2cd2d080-9622-11eb-933d-52049a086dc6.png)

