# Capstone-final-project
import matplotlib.pyplot as plt
import seaborn as sns
# ^^^ pyforest auto-imports - don't write above this line
#install packages
!pip install geopy
!pip install lxml
!pip install folium
print('Installed.')




import pandas as pd
import numpy as np
from geopy.geocoders import Nominatim 
from pandas.io.json import json_normalize 
import requests

import folium #map rendering library

# import k-means from clustering stage
from sklearn.cluster import KMeans

# Matplotlib and associated plotting modules
import matplotlib.cm as cm
import matplotlib.colors as colors

print('Libraries imported.')



import seaborn as sns
import matplotlib.pyplot as plt
