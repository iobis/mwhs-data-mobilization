# mwhs-data-mobilization

This repository centralizes biodiversity data mobilization efforts for marine World Heritage sites. This repository is organized as follows:

- [Issues](https://github.com/iobis/mwhs-data-mobilization/issues): status tracking and discussion of data sources to be processed as well as any other issues.
- Folder [datasets](datasets): raw data files and documents organized by dataset.
- Folder [output](output): combined Darwin Core Archive output for all datasets.
- Folder [notebooks](notebooks): notebooks for bundling individual datasets into a Darwin Core Archive for publishing.

## Data standards and required fields

All output will use the biodiversity data standards as [outlined in the OBIS manual](https://manual.obis.org/data_standards.html). The following data fields are highly recommended for all datasets:

| Field                      | Description                                                                                        | Darwin Core                                                |
|----------------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------|
| Date                       | Date of the occurrence.                                                                            | http://rs.tdwg.org/dwc/terms/eventDate                     |
| Location                   | Detail textual description of the location.                                                        | http://rs.tdwg.org/dwc/terms/locality              |
| Longitude                  | Longitude in decimal degrees, point location or centroid for a larger area.                        | http://rs.tdwg.org/dwc/terms/decimalLongitude              |
| Latitude                   | Latitude in decimal degrees, point location or centroid for a larger area.                         | http://rs.tdwg.org/dwc/terms/decimalLatitude               |
| Coordinate uncertainty     | Coordinate uncertainty expressed in meters from the centroid (see fields above).                   | http://rs.tdwg.org/dwc/terms/coordinateUncertaintyInMeters |
| Scientific name            | Scientific name as found in the source.                                                            | http://rs.tdwg.org/dwc/terms/scientificName                |
| Scientific name identifier | Identifier for the scientific name, preferably a full [WoRMS](https://www.marinespecies.org/) LSID | http://rs.tdwg.org/dwc/terms/scientificNameID              |
| References                 | Bibliographic references associated with the occurrence (pipe separated).                          | http://rs.tdwg.org/dwc/terms/associatedReferences          |

If a precise coordinates are not available, a spatial polygon can be provided in the [footprintWKT](http://rs.tdwg.org/dwc/terms/footprintWKT) field formatted as [WKT](https://wktmap.com/). Alternatively, a location identifier can be provided in the [locationID](http://rs.tdwg.org/dwc/terms/locationID) field, for which we recommend using identifiers from [Marine Regions](https://marineregions.org/), for example `http://marineregions.org/mrgid/26874`.

For additional fields, see the [OBIS manual](https://manual.obis.org/data_standards.html) or the [Darwin Core Quick Reference Guide](https://dwc.tdwg.org/terms/).

## How to
### Add a data source

- Create a folder in [datasets](datasets) with a descriptive name (all lowercase with underscores). Upload any data files or documents into that folder. These can be reports, research papers, spreadsheets, CSV files, etc.
- Create an issue in [Issues](https://github.com/iobis/mwhs-data-mobilization/issues) with a description of the dataset and a link to the folder created above. Describe any issues with data quality or missing data elements, and add any other information that may be relevant for data processing.