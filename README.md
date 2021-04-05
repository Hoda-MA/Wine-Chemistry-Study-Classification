# Wines-Chemistry-Study
Wine is one the most popular beverage in the world. Flavonoids include the anthocyanins and tannins which contribute to the color and mouthfeel of the wine. Many people believe that red wine comes from red grapes and white wine comes from white grapes, While this is usually the case, it is for a different reason than most would assume.

In this study, I am aimed to understand the chemistry of wine and share the result with you. For getting more familiar with the chemistry of wine, you may take a look on its pH-values. moreover, the properties of wine is dependent on the ingredients hence the pH.



![Wine_pH_scale](https://user-images.githubusercontent.com/64262003/113576525-014ee680-9620-11eb-9e43-5a94bf3fe52c.png)

# Drawing the wine molecule!
<img width="425" alt="Flavonoid" src="https://user-images.githubusercontent.com/64262003/113578025-78857a00-9622-11eb-838b-988412461778.png">


<img width="830" alt="Untitled" src="https://user-images.githubusercontent.com/64262003/113577459-97374100-9621-11eb-88a5-6135e913cd82.png">



# checking the distribution of wine classes in the table
<img width="676" alt="wUntitled" src="https://user-images.githubusercontent.com/64262003/113578347-f5185880-9622-11eb-9d68-e3ad8599c38a.png">

    
# ckecking the correlation between columns. I prefer personally the heat-map for doing this.
#correlational heat map
wine_corr=wine.iloc[:,:].corr();
plt.figure(figsize=(12,6))
sns.heatmap(wine_corr, cmap='YlGnBu', annot=True)
    plt.show()
    
![download](https://user-images.githubusercontent.com/64262003/113577826-2cd2d080-9622-11eb-933d-52049a086dc6.png)

