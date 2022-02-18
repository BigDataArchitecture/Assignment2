Assignment_2
==============================

How to run SYNRAD Generator:

Requirements: 
Python Files:
1) make_synrad_dataset.py
2) synrad_generator.py
3) utils.py 

All the above files are availabe at https://github.com/BigDataArchitecture/neurips-2020-sevir/tree/master/src/data

Data Files:
Choose any one year any one file of following img types
1) IRO69 
2) IR107
3) VIL
4) LGHT

Save it as the folder structure mentioned in CATLOG.csv or mentioned below:

    ├── Main_Folder
      ├── vil
      │   ├── 2019      <- Save the sample file inside this for VIL.
      ├── ir069
      │   ├── 2019      <- Save the sample file inside this for IR069.
      ├── ir107
      │   ├── 2019      <- Save the sample file inside this for IR107.
      ├── lght
      │   ├── 2019      <- Save the sample file inside this for LGHT.
  
Catlog.csv
Just keep records/events of those filenames which you are saving it in the above folders, delete rest all of them!
P.S we do this because the code in the py file traverse through the catlog.csv and fetch the filenames from it and if it does not find it you will get an path error

Make a empty folder output which will be used to output the testing sample

Overall Project Folder should look something like this:


    ├── Main_Folder
      ├── Output        <- Where the output will be stored.
      ├── vil
      │   ├── 2019      <- Save the sample file inside this for VIL.
      ├── ir069
      │   ├── 2019      <- Save the sample file inside this for IR069.
      ├── ir107
      │   ├── 2019      <- Save the sample file inside this for IR107.
      ├── lght
      │   ├── 2019      <- Save the sample file inside this for LGHT.
      ├── catlog.csv.       
      ├── make_synrad_dataset.py
      ├── synrad_generator.py   
      ├── utils.py   
  

Once you the setup:
Execute following code:
cd src/data

### Generate synrad training & testing datasets
python make_synrad_dataset.py --sevir_data ../../data/sevir --sevir_catalog ../../data/CATALOG.csv --output_location ../../data/interim/


Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

