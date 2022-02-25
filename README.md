Assignment_2
==============================
PART 1:
How to run SYNRAD/Nowcast Generator:

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

### Generate synrad training & testing datasets
python make_synrad_dataset.py --sevir_data ../../data/sevir --sevir_catalog ../../data/CATALOG.csv --output_location ../../data/interim/

More Deatils 👇
Google Codelab: https://codelabs-preview.appspot.com/?file_id=1i0cKXjIWksTkFbtSPx2mH4Zioa1o-oV1J3JXw49rNoE#3

