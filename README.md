Assignment_2
==============================
This assignment consists of two parts:
PART 1:
a) Generating test data for both Synrad and Nowcast usecases.
b) Running the notebooks for Synrad and Nowcast usecases.

PART 2: 
a) Designing the architecture for Nowcasting intelligence system for our usecase which is Maritime.

**PART 1**:

Brief introduction about Nowcasting and Synthetic radar(synrad): >

1. Earth's weather is continuously monitored by sensors that collect TBs of data everyday. Weather data is collected through ground based radars NEXRAD and GOES satellites. But the amount of data collected by these sources is too large and isn't "machine learning ready". To address these challenges, SEVIR dataset was designed by 3 MIT scientists. >

2. Two use cases of this SEVIR dataset are radar nowcasting(short term weather forecasts) and synthetic weather radar. >

3. **Radar nowcasting** is high resolution, short-term weather forecasts of radar echos, precipitation, cloud coverage or other meteorological quantities widely used in public safety, air traffic control and many other areas. >

4. This future prediction task takes 13 VIL images sampled at 5 minute intervals as input. The model takes this as input and it produces the next 12 images in the sequence corresponding to the next hour of weather. The model input is of size Nx384x384x13 pixels and the output is of size Nx384x384x12 pixels. >

5. **Synthetic weather radar** is generating radar like imagery of storm depictions using only satellite and lightning as inputs to the model. ir069, ir107 and lght image types are taken as input and these three image types are transformed into vil.

Lets see the procedure of part 1:

Steps 1

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

### More Details 👇
Google Codelab: https://codelabs-preview.appspot.com/?file_id=1i0cKXjIWksTkFbtSPx2mH4Zioa1o-oV1J3JXw49rNoE#0

### Part 2: Nowcasting Architecture 👇
Google Codelab: https://codelabs-preview.appspot.com/?file_id=1vDU4PUry6cB-0SMbEo7oPp-YSTL1wquu2rJqpBVut9o#0



