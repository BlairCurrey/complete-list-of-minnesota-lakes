# Complete List of Lakes in Minnesota

Minnesota is proudly known as the land of 10,000 lakes but it's not so easy to find data on more than a subset of them. This dataset is the most complete list of lakes in Minnesota that I was able to put together. I was searching for this dataset myself but was surprised to find woefully incomplete sources. The sources found only included about 2000-4000 lakes, while Minnesota officially recognizes 11,842.

This dataset includes [`lakes-and-ponds.csv`](lakes-and-ponds.csv) which includes all `"Lake or Pond"` records from a MN DNR source and excludes duplicate records and sub-basins (such as bays, lake sections, etc). The other dataset is [`lakes.csv`](lakes.csv), which includes all records in `lakes-and-ponds.csv` that are 10 acres or more in size. This dataset actually includes more than Minnesota's official tally of 11,842 which indicates further refinement may be needed to remove extraneous records.

### Data Features
|       |      name |      acres | shore_miles | County   |
|------:|----------:|-----------:|------------:|----------|
|     0 |      Bugo |  30.377878 |    1.016194 |     Lake |
|     1 |  Pea Soup |  12.101236 |    0.623966 |     Lake |
|     2 |   Sundown |  19.021747 |    0.721198 |     Lake |
|     3 |   Unnamed |  18.746844 |    0.633619 |   Aitkin |
|     4 | Studhorse |  19.658274 |    0.722163 |   Aitkin |
|   ... |       ... |        ... |         ... |      ... |
| 14057 |     Grave | 372.807961 |    6.189930 |     Cass |
| 14058 |    Jensen |  52.293865 |    2.075376 |   Dakota |
| 14059 |     Welch | 196.064298 |    2.230892 |     Cass |
| 14060 |    German | 888.773305 |    7.148789 | Le Sueur |
| 14061 |      Long | 131.010846 |    4.037602 |   Itasca |


## Methodology
These datasets were put together from the [Hydrography Dataset from the Minnesota DNR](https://gisdata.mn.gov/dataset/water-dnr-hydrography). This involved loading the layer into QGIS and exporting the attribute table to [`mn-dnr-hydro-features.csv`](mn-dnr-hydro-features.csv). The data was then cleaned in [`clean-mn-dnr-dataset.ipynb`](clean-mn-dnr-dataset.ipynb) according to the process expounded upon in the notebook.

## Areas for improvement
- Filter further to remove extraneous records.
- New features:
    - **Coordinates**: Could perhaps translate X, Y coordinates in Qgis.
    - **Depth**: This may require a better data source. Partial sources exist for this but would likely be hard to merge given the amount of lakes with duplicate names. Could be possible if both datasets include coordinates.
- I believe the USGS maintains similar hydrography datasets. These sources might be better, or are at least worth comparing against.