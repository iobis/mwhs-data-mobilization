# mwhs-data-mobilization

This repository centralizes biodiversity data mobilization efforts for marine World Heritage sites. This repository is organized as follows:

```
├── README.md                 : Description of this repository (this file)
├── index.html                : Dataset overview to track mobilization status
├── .gitignore                : Files and directories to be ignored by git
|── .gitmodules               : Submodule information for git
│
├── datasets
│   ├── site1
│   |   ├── dataset1
│   |   |   ├── raw		   : Directory containing raw datafiles (PDFs, CSVs, etc.)
│   |   |   └── processed     : Directory containing processed datafiles (OCRed files, saved CSV tables, etc.)
│   |   ├── dataset2
│   |   └── dataset...
│   ├── site2
│   └── site...
│
├── notebooks
│   ├── site1
│   |   ├── dataset1
│   |   |   ├── dataset.Rproj  : R Project file for the dataset
│   |   |   ├── index.Rmd      : R Markdown script for mobilization
│   |   |   └── index.html     : R Markdown HTML document for visualization
│   |   ├── dataset2
│   |   └── dataset...
│   ├── site2
│   └── site...
|
├── output
│   ├── site1
│   |   ├── dataset1
│   |   |   └── DwC-A.zip     : DarwinCore-Archive
│   |   ├── dataset2
│   |   └── dataset...
│   ├── site2
│   └── site...
|
└── scripts_data
    ├── pdf_to_tables         : Submodule repository of the OCR/table parsing script
    └── meta_occurrence_checklist_template.xml  : meta.xml file template for Occurrence Core data
```


- Directory [datasets](datasets): raw data files and documents organized by site and dataset.
- Directory [notebooks](notebooks): notebooks for bundling individual datasets into a Darwin Core Archive for publishing.
- Directory [output](output): combined Darwin Core Archive output for all sites and datasets.
- Directory [scripts_data](scripts_data): shared scripts and template files.

All sites are listed in each of the three major directories, with associated datasets nested under the appropriate site.

## Data standards and required fields

Guidelines for mobilizing data are based on [A checklist recipe: making species data open and FAIR](https://academic.oup.com/database/article/doi/10.1093/database/baaa084/5979745) and associated code: [Checklist Recipe](https://trias-project.github.io/checklist-recipe/dwc_mapping.html)

All output will use the biodiversity data standards as [outlined in the OBIS manual](https://manual.obis.org/data_standards.html). The following data fields are highly recommended for all occurrence datasets:

| Field                      | Description                                                                                        | Darwin Core                                                |
|----------------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------|
| Date                       | Date of the occurrence.                                                                            | http://rs.tdwg.org/dwc/terms/eventDate                     |
| Location                   | Detailed textual description of the location.                                                        | http://rs.tdwg.org/dwc/terms/locality              |
| Longitude                  | Longitude in decimal degrees, point location or centroid for a larger area.                        | http://rs.tdwg.org/dwc/terms/decimalLongitude              |
| Latitude                   | Latitude in decimal degrees, point location or centroid for a larger area.                         | http://rs.tdwg.org/dwc/terms/decimalLatitude               |
| Coordinate uncertainty     | Coordinate uncertainty expressed in meters from the centroid (see fields above).                   | http://rs.tdwg.org/dwc/terms/coordinateUncertaintyInMeters |
| Scientific name            | Scientific name as found in the source.                                                            | http://rs.tdwg.org/dwc/terms/scientificName                |
| Scientific name identifier | Identifier for the scientific name, preferably a full [WoRMS](https://www.marinespecies.org/) LSID | http://rs.tdwg.org/dwc/terms/scientificNameID              |

If a precise coordinates are not available, a spatial polygon can be provided in the [footprintWKT](http://rs.tdwg.org/dwc/terms/footprintWKT) field formatted as [WKT](https://wktmap.com/). Alternatively, a location identifier can be provided in the [locationID](http://rs.tdwg.org/dwc/terms/locationID) field, for which we recommend using identifiers from [Marine Regions](https://marineregions.org/), for example `http://marineregions.org/mrgid/26874`.

For additional fields, see the [OBIS manual](https://manual.obis.org/data_standards.html) or the [Darwin Core Quick Reference Guide](https://dwc.tdwg.org/terms/).
