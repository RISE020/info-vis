## Dataset and Preprocessing

After settling on the topic of Schiphol, we started searching for our datasets. The [first dataset](https://www.schiphol.nl/nl/schiphol-group/pagina/verkeer-en-vervoer-cijfers/), provided by Schiphol, contains information about the monthly traffic at Schiphol since January 1992. Finding a second dataset was more challenging than expected. Many of the RIVM datasets were provided in `.rdf` format and contained insufficient data or were unable to be read at all. We then stumbled upon a dataset containing the emission of fine particulate matter as measured from eight measuring points around Schiphol. Although this dataset was exactly what we were looking for, it only contained data from 2017 and 2018. Having not found an alternative, we used this dataset for the project proposal. After the proposal, we found a [third dataset](https://www.emissieregistratie.nl/data/vliegvelden), provided by the 'Rijksoverheid', containing the emission of a number of substances from 1990 till 2022 at different airports in the Netherlands. The first and third datasets were used for the final deliverable.

### Cleaning

All the datasets came in `.xlsx` format and were adjusted to `.csv` to be further processed using the Pyhton pandas library. 

The first dataset, containing Schiphol airport's monthly traffic data, was cleaned first. Initially, we removed all unnamed columns and rows that only served a visual purpose in the original .xlsx file. We also ensured that all string types were converted to float types where necessary. Next, we decided to save the total yearly data instead of the total monthly data. This decision was made because the second dataset also presented its information per year.

The second dataset contained the emission data for all airports in the Netherlands, with 12 columns and 40,316 rows, of which only 2,960 rows contained information about Schiphol airport. We isolated these rows and saved them in a new dataframe. To further clean up the dataset, we dropped irrelevant columns.

### Variables

The variables in the first and second dataset can be classified under:

- Continuous / Ratio variables:
`Year`
`Air_Transport_Movements_Europe`
`Air_Transport_Movements_Intercontinental`
`Air_Transport_Movements_Total`
`Passengers_Europe`
`Passengers_Intercontinental`
`Passengers_Total*`
`Passengers_O&D`
`Passengers_Transfer`
`Passengers_Total*.1`
`Passengers_Scheduled`
`Passengers_Non Scheduled`
`Passengers_Transit direct`
`Passengers_Total`
`Cargo (tonnes)`
`Mail (tonnes)`
`EMISSIE (kg)`

- Discrete / Ordinal variables: None in the given datasets.

- Discrete / Nominal variables:
`VLIEGVELD`
`VLIEGVELD_CODE`
`STOFNAAM`
`STOF_CODE`
`COMPARTIMENT`
`COMPARTIMENT_CODE`
`EMISSIEOORZAAK`
`EMISSIEOORZAAK_CODE`

- Discrete / Interval variables: None in the given datasets.

- Discrete / Ratio variables: None in the given datasets.
