# Wines-Chemistry-Study
Wine is one the most popular beverage in the world. Flavonoids include the anthocyanins and tannins which contribute to the color and mouthfeel of the wine. Many people believe that red wine comes from red grapes and white wine comes from white grapes, While this is usually the case, it is for a different reason than most would assume.

In this study, I am aimed to understand the chemistry of wine and share the result with you. For getting more familiar with the chemistry of wine, you may take a look on its pH-values. moreover, the properties of wine is dependent on the ingredients hence the pH.



![Wine_pH_scale](https://user-images.githubusercontent.com/64262003/113576525-014ee680-9620-11eb-9e43-5a94bf3fe52c.png)

# This is how the Flavonoid Molecules look like :)
from IPython.display import SVG
from rdkit import Chem
from rdkit import Chem
from rdkit.Chem import rdDepictor
from rdkit.Chem.Draw import rdMolDraw2D
# Create mol object from smiles string
mol = Chem.MolFromSmiles('C1=CC=C(C=C1)C2=CC(=O)C3=CC=CC=C3O2')
molSize=(450,250)

mc = Chem.Mol(mol.ToBinary())
if not mc.GetNumConformers():
#....#Compute 2D coordinates
    rdDepictor.Compute2DCoords(mc)
# init the drawer with the size
    drawer = rdMolDraw2D.MolDraw2DSVG(molSize[0],molSize[1])
#draw the molcule
drawer.DrawMolecule(mc)
drawer.FinishDrawing()
# get the SVG string
svg = drawer.GetDrawingText()
# fix the svg string and display it
display(SVG(svg.replace('svg:','')))
<img width="425" alt="Flavonoid" src="https://user-images.githubusercontent.com/64262003/113576566-14fa4d00-9620-11eb-83aa-87f19af3b7ef.png">

### after calling the libraries (please refer to the main code), we can start.
wine=pd.read_csv('wine.csv')
wine.head()


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

