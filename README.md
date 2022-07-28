# netflix-starter-code
-------------------------------
import pandas as pd
import matplotlib.pyplot as plt
import scipy.stats as st
import numpy as np
-------------------------------
credit_data_csv = "Resources/credits.csv"
title_data_csv = "Resources/titles.csv"

# load data into a pandas data frame
credit_data = pd.read_csv(credit_data_csv)
title_data = pd.read_csv(title_data_csv)

# merge the two datasets into a single data frame 
mergedDF = pd.merge(title_data, credit_data, how="left", on=["id"])
mergedDF.head()
-------------------------------
# drop the TV shows from the data frame
moviesDF = mergedDF.drop(mergedDF[mergedDF["type"]=='SHOW'].index)
moviesDF
