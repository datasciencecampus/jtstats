## Retrieval of JTS data using the Python module
The Python version of the module allows easy retrieval of the JTS data using the ````get_jts()```` function. The key parameters that can be specified in order to specify what data to retrieve are: ````type_code````, ````spec````, ````sheet```` and ````table_code```` (even though this last parameter is only rarely needed). The table here reports the values to be used for these parameters in order to retrieve each of the JTS data. In some cases, the ````spec```` parameter should be set to empty and the ````sheet```` parameter should be used instead. These occurrences are indicated with $^\S$ in the table below. For all other occurrences, the ````sheet```` parameter should be simply set to the year for which data is needed, e.g. ````sheet = '2019'````. The ````get_jts()```` function returns a ````pandas```` dataframe. The size of the returned dataframe is given in the last column (in the format #rows $\times$ #columns}) of the table, for the specific case of 2019 data. Notes: $^\star$ here, public transport also includes walking. Walking was introduced as a separate mode of travel only for 2019 data. $^\S$ this value should actually be used for the ````sheet```` parameter in the ````get_jts()```` function, and the ````spec```` parameter should be left empty. $^\dagger$ this value should be used in the ````table_code```` parameter in the ````get_jts()```` function, and the ````type_code```` parameter should be left unspecified.

| Table title | Description                                                            | Type code      | Spec/Sheet       | Size              |
|-------------|--------------------------------------------------------------------------------------------|----------------|------------------|-------------------|
| JTS0101     | Travel time to reach nearest key services by mode of travel (England)                      | jts01          | JTS0101$^\S$     | $16 \times 12$    |
| JTS0102     | Travel time to reach nearest key services by mode of travel (by urban/rural)               | jts01          | urban            | $48 \times 14$    |
| JTS0103     | Travel time to reach nearest key services by mode of travel (by region)                    | jts01          | region           | $36 \times 13$    |
| JTS0104     | Travel time to reach nearest key services by mode of travel (by local authority)           | jts01          | local authority  | $361\times 7$     |
| JTS0201     | Access to key services within journey times by mode of travel (England)                    | jts02          |                  | 32$\times$ 13     |
| JTS0202     | Access to key services within journey times by mode of travel (by urban/rural)             | jts02          | urban            | 64$\times$ 14     |
| JTS0203     | Access to key services within journey times by public transport$^\star$ (by region)        | jts02          | public transport | 71$\times$ 13     |
| JTS0204     | Access to key services within journey times by cycle (by region)                           | jts02          | cycle            | 71$\times$ 13     |
| JTS0205     | Access to key services within journey times by car (by region)                             | jts02          | car              | 71$\times$ 13     |
| JTS0206     | Access to key services within journey times by walking (by region)                         | jts0206$^\dagger$ |                  | 71$\times$ 13     |
| JTS0301     | Number of sites within journey time by key services and mode of travel (England)           | jts03          |                  | 19$\times$ 13     |
| JTS0302     | Number of sites within journey time by key services and mode of travel (urban/rural)       | jts03          | urban            | 32$\times$ 15     |
| JTS0303     | Number of sites within journey time by key services and public transport$^\star$ (regions) | jts03          | public transport | 36$\times$ 14     |
| JTS0304     | Number of sites within journey time by key services and cycle (regions)                    | jts03          | cycle            | 36$\times$ 14     |
| JTS0305     | Number of sites within journey time by key services and car (regions)                      | jts03          | car              | 36$\times$ 14     |
| JTS0306     | Number of sites within journey time by key services and walking (regions)                  | jts0306$^\dagger$ |                  | 36$\times$ 14     |
| JTS0401     | Journey times for employment centres by mode of travel (local authority)                   | jts04          | employment       | 361$\times$ 112   |
| JTS0402     | Journey times for primary schools by mode of travel (local authority)                      | jts04          | primary          | 361$\times$ 40    |
| JTS0403     | Journey times for secondary schools by mode of travel (local authority)                    | jts04          | secondary        | 361$\times$ 40    |
| JTS0404     | Journey times for further education by mode of travel (local authority)                    | jts04          | further          | 361$\times$ 40    |
| JTS0405     | Journey times for GPs by mode of travel (local authority)                                  | jts04          | gp               | 361$\times$ 40    |
| JTS0406     | Journey times for hospitals by mode of travel (local authority)                            | jts04          | hospital         | 361$\times$ 40    |
| JTS0407     | Journey times for food stores by mode of travel (local authority)                          | jts04          | food             | 361$\times$ 40    |
| JTS0408     | Journey times for town centres by mode of travel (local authority)                         | jts04          | town             | 361$\times$ 40    |
| JTS0409     | Journey times to pharmacy by cycle and car (local authority)                               | jts04          | pharmacy         | 361$\times$ 22    |
| JTS0501     | Journey times for employment centres by mode of travel (LSOA)                              | jts05          | employment       | 32844$\times$ 113 |
| JTS0502     | Journey times for primary schools by mode of travel (LSOA)                                 | jts05          | primary          | 32844$\times$ 41  |
| JTS0503     | Journey times for secondary schools by mode of travel (LSOA)                               | jts05          | secondary        | 32844$\times$ 41  |
| JTS0504     | Journey times for further education by mode of travel (LSOA)                               | jts05          | further          | 32844$\times$ 41  |
| JTS0505     | Journey times for GPs by mode of travel (LSOA)                                             | jts05          | gp               | 32844$\times$ 41  |
| JTS0506     | Journey times for hospitals by mode of travel (LSOA)                                       | jts05          | hospital         | 32844$\times$ 41  |
| JTS0507     | Journey times for food stores by mode of travel (LSOA)                                     | jts05          | food             | 32844$\times$ 41  |
| JTS0508     | Journey times for town centres by mode of travel (LSOA)                                    | jts05          | town             | 32844$\times$ 41  |
| JTS0509     | Journey times to pharmacy by cycle and car (LSOA)                                          | jts05          | pharmacy         | 32844$\times$ 23  |


## Retrieval of JTS data using the Python module ( JTS09)
As in the table above, we report here how to retrieve the JTS data using the Python package. In particular, this table focuses on the journey times connectivity (JTS09) data, which have a slightly different format than the rest. For this reason, the table includes separately the ````spec```` and ````sheet```` parameters, since in most cases here they both need to be set in order to retrieve the correct data.

| Table title | Description                                      | Type code | Spec     | Sheet             | Size             |
|-------------|----------------------------------------------------------------------|-----------|----------|-------------------|------------------|
| JTS0901     | Journey times to nearest airports (local authority)                  | jts09     | airports | JTS0901_Nearest  | 128$\times$ 6    |
| JTS0901     | Journey times to selected airports (local authority)                 | jts09     | airports | JTS0901_Selected | 128$\times$ 44   |
| JTS0902     | Catchment population measures for airports (local authority)         | jts09     | airports | JTS0902           | 32$\times$ 14    |
| JTS0903     | Population within journey time of airports (local authority)         | jts0903   | airports | JTS0903           | 130$\times$ 9    |
| JTS0904     | Number airports within journey time (local authority)                | jts09     | airports | JTS0904           | 129$\times$ 9    |
| JTS0905     | Journey times to selected airports (LSOA)                            | jts09     | airports | JTS0905_Selected | 32844$\times$ 41 |
| JTS0905     | Journey times to airports, summary (LSOA)                            | jts09     | airports | JTS0905_Summary  | 32844$\times$ 9  |
| JTS0921     | Journey times to nearest rail stations (local authority)             | jts09     | rail     | JTS0921_Nearest  | 119$\times$ 7    |
| JTS0921     | Journey times to rail stations by car (local authority)              | jts09     | rail     | car               | 120$\times$ 81   |
| JTS0921     | Journey times to rail stations by public transport (local authority) | jts09     | rail     | PT                | 120$\times$ 81   |
| JTS0922     | Catchment population measures for rail stations (England)            | jts09     | rail     | JTS0922           | 79$\times$ 15    |
| JTS0923     | Population within journey time of rail stations (local authority)    | jts09     | rail     | JTS0923           | 130$\times$ 10   |
| JTS0924     | Number of rail stations within journey time (local authority)        | jts09     | rail     | JTS0924           | 129$\times$ 9     |
| JTS0925     | Journey times by public transport for selected rail stations (LSOA)  | jts09     | rail     | JTS0925_Selected | 32844$\times$ 84 |
| JTS0925     | Journey times by public transport for rail stations, summary (LSOA)  | jts09     | rail     | JTS0926_Summary  | 32844$\times$ 7  |
| JTS0926     | Journey times by car for selected rail stations (LSOA)               | jts09     | rail     | JTS0926_Selected | 32844$\times$ 84 |
| JTS0926     | Journey times by car for rail stations, summary (LSOA)               | jts09     | rail     | JTS0926_Summary  | 32844$\times$ 7  |
| JTS0930     | Travel time to city centres (local authority)                        | jts09     |          | JTS0930_LA       | 361$\times$ 5    |
| JTS0930     | Travel time to city centres (LSOA)                                   | jts09     |          | JTS0930_LSOA     | 32844$\times$ 6  |

