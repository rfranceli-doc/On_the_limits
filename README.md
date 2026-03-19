# On_the_limits
Datasets and notebooks to reproduce experiments from "On the Limits of Genetically-Optimized Homogeneous Ensembles for Credit Risk Classification"

The dataset is available in "https://www.kaggle.com/datasets/wordsforthewise/lending-club/data?select=accepted_2007_to_2018Q4.csv.gz".

Cells 3 and 4 in the ipynb can be replaced by the code below for direct Kaggle access. When running the code, you will be prompted for your Kaggle username and API key. Since the file is large, this ensures there is no need to move it between repositories.

# Install API 
!pip install kaggle -q

# Upload do kaggle.json (1st time)
from google.colab import files
files.upload()  # enter your kaggle.json data

# Credentials
!mkdir -p ~/.kaggle
!mv kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json

# Requested file
!kaggle datasets download -d wordsforthewise/lending-club \
  --file accepted_2007_to_2018Q4.csv.gz \
  -p ./data/

# Read .gz
df_accepted = pd.read_csv("./data/accepted_2007_to_2018Q4.csv.gz", compression="gzip")

print(df_accepted.shape)
