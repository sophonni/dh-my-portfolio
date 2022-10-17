---
layout: page
title: Crowdsourced-Data Normalization with Python and Pandas
description: This lesson describes crowdsourcing as a form of data creation as well as how pandas can be used to prepare a crowdsourced dataset for analysis. This lesson covers managing duplicate and missing data and explains the difficulties of dealing with dates.
---

## Source
[Brandon Walsh, "Crowdsourced-Data Normalization with Python and Pandas" Programming Historian, https://doi.org/10.46430/phen0078.](https://programminghistorian.org/en/lessons/crowdsourced-data-normalization-with-pandas)

## Reflection
Crowdsourcing is a way of outsourcing work by utilizing the input and contributions of people through an online platform. It is a way of collecting ideas, receiving input, or gathering data from the public, the proverbial “crowd.” There are many reasons a project may choose to use crowdsourcing as a method to gather data and input. Crowdsourcing lets you make use of the contributions of a diverse group of individuals, all with different skills and strengths. Crowdsourcing can be used for idea generation or for data collection and text transcription or translation. Projects of this nature are increasing as organizations such as libraries work to make their very large collections accessible online.

By completing this specific programming historian, I've learned how to open a file containing data and read them. I've also learned how to work with a big collection of data where it's being separated by columns and rows and how to use built-in functions in order to manipulate the dataset in order to only retrieve the necessary data needed to study.



## Code
```python
import pandas as pd

df = pd.read_csv("Menu.csv")    #read data from the file and load it to pandas DataFrame
print(df.head())    #view the first five row of the dataset
```

          id name                     sponsor                 event       venue  \
    0  12463  NaN               HOTEL EASTMAN             BREAKFAST  COMMERCIAL   
    1  12464  NaN            REPUBLICAN HOUSE              [DINNER]  COMMERCIAL   
    2  12465  NaN  NORDDEUTSCHER LLOYD BREMEN  FRUHSTUCK/BREAKFAST;  COMMERCIAL   
    3  12466  NaN  NORDDEUTSCHER LLOYD BREMEN                LUNCH;  COMMERCIAL   
    4  12467  NaN  NORDDEUTSCHER LLOYD BREMEN               DINNER;  COMMERCIAL   
    
                                    place         physical_description occasion  \
    0                     HOT SPRINGS, AR              CARD; 4.75X7.5;  EASTER;   
    1                    MILWAUKEE, [WI];   CARD; ILLUS; COL; 7.0X9.0;  EASTER;   
    2  DAMPFER KAISER WILHELM DER GROSSE;    CARD; ILLU; COL; 5.5X8.0;      NaN   
    3  DAMPFER KAISER WILHELM DER GROSSE;    CARD; ILLU; COL; 5.5X8.0;      NaN   
    4  DAMPFER KAISER WILHELM DER GROSSE;  FOLDER; ILLU; COL; 5.5X7.5;      NaN   
    
                                                   notes call_number  keywords  \
    0                                                NaN   1900-2822       NaN   
    1  WEDGEWOOD BLUE CARD; WHITE EMBOSSED GREEK KEY ...   1900-2825       NaN   
    2  MENU IN GERMAN AND ENGLISH; ILLUS, STEAMSHIP A...   1900-2827       NaN   
    3  MENU IN GERMAN AND ENGLISH; ILLUS, HARBOR SCEN...   1900-2828       NaN   
    4  MENU IN GERMAN AND ENGLISH; ILLUS, HARBOR SCEN...   1900-2829       NaN   
    
       language       date                    location  location_type currency  \
    0       NaN  4/15/1900               Hotel Eastman            NaN      NaN   
    1       NaN  4/15/1900            Republican House            NaN      NaN   
    2       NaN  4/16/1900  Norddeutscher Lloyd Bremen            NaN      NaN   
    3       NaN  4/16/1900  Norddeutscher Lloyd Bremen            NaN      NaN   
    4       NaN  4/16/1900  Norddeutscher Lloyd Bremen            NaN      NaN   
    
      currency_symbol    status  page_count  dish_count  
    0             NaN  complete           2          67  
    1             NaN  complete           2          34  
    2             NaN  complete           2          84  
    3             NaN  complete           2          63  
    4             NaN  complete           4          33  



```python
print(df.columns)    #display the column headers
```

    Index(['id', 'name', 'sponsor', 'event', 'venue', 'place',
           'physical_description', 'occasion', 'notes', 'call_number', 'keywords',
           'language', 'date', 'location', 'location_type', 'currency',
           'currency_symbol', 'status', 'page_count', 'dish_count'],
          dtype='object')


## Removing Columns


```python
dropped_col = ['notes', 'call_number', 'currency', 'currency_symbol', 'physical_description', 'status']    #list containing column we want to remove
df.drop(dropped_col, inplace=True, axis=1)    #second parameter specify to remove colunm when its header correspond to the above list
                                              #axis means specify columns
                                              #lable means specify rows
```


```python
print(df.shape)    #display the current number of rows, columns
```

    (17546, 14)


## Duplicates


```python
print(df[df.duplicated(keep=False)])    #keep=false means mark every duplicates as true and return duplicate rows
```

              id name        sponsor      event       venue            place  \
    0      12463  NaN  HOTEL EASTMAN  BREAKFAST  COMMERCIAL  HOT SPRINGS, AR   
    17545  12463  NaN  HOTEL EASTMAN  BREAKFAST  COMMERCIAL  HOT SPRINGS, AR   
    
          occasion  keywords  language       date       location  location_type  \
    0      EASTER;       NaN       NaN  4/15/1900  Hotel Eastman            NaN   
    17545  EASTER;       NaN       NaN  4/15/1900  Hotel Eastman            NaN   
    
           page_count  dish_count  
    0               2          67  
    17545           2          67  



```python
df[df.duplicated(subset='id', keep=False)]    #check for duplicate column
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>name</th>
      <th>sponsor</th>
      <th>event</th>
      <th>venue</th>
      <th>place</th>
      <th>occasion</th>
      <th>keywords</th>
      <th>language</th>
      <th>date</th>
      <th>location</th>
      <th>location_type</th>
      <th>page_count</th>
      <th>dish_count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>12463</td>
      <td>NaN</td>
      <td>HOTEL EASTMAN</td>
      <td>BREAKFAST</td>
      <td>COMMERCIAL</td>
      <td>HOT SPRINGS, AR</td>
      <td>EASTER;</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4/15/1900</td>
      <td>Hotel Eastman</td>
      <td>NaN</td>
      <td>2</td>
      <td>67</td>
    </tr>
    <tr>
      <th>17545</th>
      <td>12463</td>
      <td>NaN</td>
      <td>HOTEL EASTMAN</td>
      <td>BREAKFAST</td>
      <td>COMMERCIAL</td>
      <td>HOT SPRINGS, AR</td>
      <td>EASTER;</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4/15/1900</td>
      <td>Hotel Eastman</td>
      <td>NaN</td>
      <td>2</td>
      <td>67</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.drop_duplicates(inplace=True)    #remove duplicate rows
                                    #inplace=true means keep atleast 1 row
```


```python
print(df.shape)
```

    (17545, 14)


## Missing Data


```python
print(df.isnull().sum())    #report the column headers and number of NULL values for each column
                            #result shows that only 4 columns of the dataset are NULL-free
```

    id                   0
    name             14348
    sponsor           1561
    event             9391
    venue             9426
    place             9422
    occasion         13754
    keywords         17545
    language         17545
    date               586
    location             0
    location_type    17545
    page_count           0
    dish_count           0
    dtype: int64


## Removing Columns Based on Missing Data


```python
menu = df.dropna(thresh=df.shape[0]*0.25,how='all',axis=1)
#thresh=df.shape[0]*2.05 specify the percentage of rows to meet the criteria
#how=all means dropping the whole column
#axis=1 specify working with column
```


```python
print(menu.shape)
```

    (17545, 9)


## Remove Rows With Missing Data


```python
dropped_na = menu.dropna()
print(dropped_na)
```

              id                                            sponsor  \
    0      12463                                      HOTEL EASTMAN   
    1      12464                                   REPUBLICAN HOUSE   
    2      12465                         NORDDEUTSCHER LLOYD BREMEN   
    3      12466                         NORDDEUTSCHER LLOYD BREMEN   
    4      12467                         NORDDEUTSCHER LLOYD BREMEN   
    ...      ...                                                ...   
    10212  27695  CONFRERIE DE LA CHAINE DES ROTISSEURS, NEW ORL...   
    10213  27696  CONFRERIE DE LA CHAINE DES ROTISSEURS, GEORGIA...   
    10214  27697                                  FRANKFURTER STUBB   
    10215  27698                             HOTEL EUROPAISCHER HOF   
    10216  27699  CONFRERIE DE LA CHAINE DES ROTISSEURS, OKLAHOM...   
    
                                          event                 venue  \
    0                                 BREAKFAST            COMMERCIAL   
    1                                  [DINNER]            COMMERCIAL   
    2                      FRUHSTUCK/BREAKFAST;            COMMERCIAL   
    3                                    LUNCH;            COMMERCIAL   
    4                                   DINNER;            COMMERCIAL   
    ...                                     ...                   ...   
    10212                                DINNER  OTHER (PRIVATE CLUB)   
    10213                                DINNER  OTHER (PRIVATE CLUB)   
    10214                            DAILY MENU            HOTEL; FOR   
    10215                                DINNER            HOTEL; FOR   
    10216  INAUGURATION OF THE OKLAHOME CHAPTER  OTHER (PRIVATE CLUB)   
    
                                                       place       date  \
    0                                        HOT SPRINGS, AR  4/15/1900   
    1                                       MILWAUKEE, [WI];  4/15/1900   
    2                     DAMPFER KAISER WILHELM DER GROSSE;  4/16/1900   
    3                     DAMPFER KAISER WILHELM DER GROSSE;  4/16/1900   
    4                     DAMPFER KAISER WILHELM DER GROSSE;  4/16/1900   
    ...                                                  ...        ...   
    10212                     PLIMSOLL CLUB, NEW ORLEANS, LA  5/13/1968   
    10213        PIEDMONT DRIVING  CLUB,  [ATLANTA?] GEORGIA  5/18/1968   
    10214       HOTEL FRANKFURTER, FRANFURT AM MAIN, GERMANY   6/3/1968   
    10215                                HEIDELBERG, GERMANY  6/26/1968   
    10216  OKLAHOMA CITY GOLF AND COUNTRY CLUB, OKLAHOMA ...   7/1/1968   
    
                                                    location  page_count  \
    0                                          Hotel Eastman           2   
    1                                       Republican House           2   
    2                             Norddeutscher Lloyd Bremen           2   
    3                             Norddeutscher Lloyd Bremen           2   
    4                             Norddeutscher Lloyd Bremen           4   
    ...                                                  ...         ...   
    10212  Confrerie De La Chaine Des Rotisseurs, New Orl...           5   
    10213              Confrerie De La Chaine Des Rotisseurs           3   
    10214              Confrerie De La Chaine Des Rotisseurs           3   
    10215  Confrerie De La Chaine Des Rotisseurs, New Orl...           1   
    10216              Confrerie De La Chaine Des Rotisseurs           4   
    
           dish_count  
    0              67  
    1              34  
    2              84  
    3              63  
    4              33  
    ...           ...  
    10212          37  
    10213          22  
    10214          34  
    10215          31  
    10216          24  
    
    [7236 rows x 9 columns]


## Dealing with Dates


```python
replaced_dates = dropped_na.replace('0190-03-06', '12-31-2200')
#1st argument is what we want to replace
#2nd argument is what we want to replace it with
```

## Saving to CSV


```python
replaced_dates.to_csv("NYPL_NormalMenus.csv")    #report or send motified data to a file
```


```python

```
