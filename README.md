# Capstone-final-project
import matplotlib.pyplot as plt
import seaborn as sns
# ^^^ pyforest auto-imports - don't write above this line
#install packages
!pip install geopy
!pip install lxml
!pip install folium
print('Installed.')

Requirement already satisfied: geopy in c:\users\robuj\anaconda3\lib\site-packages (2.0.0)
Requirement already satisfied: geographiclib<2,>=1.49 in c:\users\robuj\anaconda3\lib\site-packages (from geopy) (1.50)
Requirement already satisfied: lxml in c:\users\robuj\anaconda3\lib\site-packages (4.3.4)
Requirement already satisfied: folium in c:\users\robuj\anaconda3\lib\site-packages (0.11.0)
Requirement already satisfied: jinja2>=2.9 in c:\users\robuj\anaconda3\lib\site-packages (from folium) (2.10.1)
Requirement already satisfied: numpy in c:\users\robuj\anaconda3\lib\site-packages (from folium) (1.16.4)
Requirement already satisfied: requests in c:\users\robuj\anaconda3\lib\site-packages (from folium) (2.24.0)
Requirement already satisfied: branca>=0.3.0 in c:\users\robuj\anaconda3\lib\site-packages (from folium) (0.4.1)
Requirement already satisfied: MarkupSafe>=0.23 in c:\users\robuj\anaconda3\lib\site-packages (from jinja2>=2.9->folium) (1.1.1)
Requirement already satisfied: urllib3!=1.25.0,!=1.25.1,<1.26,>=1.21.1 in c:\users\robuj\anaconda3\lib\site-packages (from requests->folium) (1.24.2)
Requirement already satisfied: chardet<4,>=3.0.2 in c:\users\robuj\anaconda3\lib\site-packages (from requests->folium) (3.0.4)
Requirement already satisfied: idna<3,>=2.5 in c:\users\robuj\anaconda3\lib\site-packages (from requests->folium) (2.8)
Requirement already satisfied: certifi>=2017.4.17 in c:\users\robuj\anaconda3\lib\site-packages (from requests->folium) (2019.6.16)
Installed.


import pandas as pd
import numpy as np
from geopy.geocoders import Nominatim 
from pandas.io.json import json_normalize 
import requests

import folium #map rendering library
Libraries imported.

# import k-means from clustering stage
from sklearn.cluster import KMeans

# Matplotlib and associated plotting modules
import matplotlib.cm as cm
import matplotlib.colors as colors

print('Libraries imported.')



import seaborn as sns
import matplotlib.pyplot as plt



Paris
paris = pd.read_csv('fr_postal_codes.csv',sep = ',',encoding = 'latin-1')
paris.head()
Postal Code	Place Name	State	County	City	Latitude	Longitude
0	24000	Périgueux	Aquitaine	Dordogne	Arrondissement de Périgueux	45.1833	0.7167
1	24001 CEDEX	Périgueux	Aquitaine	Dordogne	Arrondissement de Périgueux	45.1833	0.7167
2	24002 CEDEX	Périgueux	Aquitaine	Dordogne	Arrondissement de Périgueux	45.1833	0.7167
3	24003 CEDEX	Périgueux	Aquitaine	Dordogne	Arrondissement de Périgueux	45.1833	0.7167
4	24004 CEDEX	Périgueux	Aquitaine	Dordogne	Arrondissement de Périgueux	45.1833	0.7167

paris.dropna()
paris.head()
