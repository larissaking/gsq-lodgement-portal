# GSQ Lodgement Portal

## Purpose of this document
Provide a specification for the new GSQ Lodgement Portal that:  
* Accurately defines the business requirements
* Is a key input to software design for a software developer  

The primary input into this document is the data model defined in the [Resources Industry Report Profile](https://github.com/geological-survey-of-queensland/industry-report-profile).

## Background
Resource authority holders need to submit a range of statutory reports on their activities. Reports include all mineral exploration, geothermal exploration, greenhouse gas exploration, petroleum exploration, petroleum well, seismic survey or airborne geophysical survey, mineral development licence, petroleum lease, and petroleum pipeline licence reports and some other exploration related reporting.

When government issues a permit to a holder, the legislation requires a permit holder to submit reports to the Department when certain activities are performed under the conditions of the permit.  
* The reports contain knowledge of the geological resource.  
* Historically, industry reports have been lodged through QDEX Reports.  
* GDMP will deliver a new lodgement portal to replace QDEX Reports.  
* Most industry reports have a confidentiality period before becoming open file.  

## The Lodgement Portal

### Objectives of the Lodgement Portal
1. Provide a single portal for industry and GSQ to lodge georesources reports.
2. Provide data validation at point of data entry.
3. Provide a database store to store in-progress and submitted reports.
4. Harvest the submitted metadata, data and datasets for insertion into CKAN, S3 and the [GeoProperties Database](https://github.com/geological-survey-of-queensland/ssor-database).
5. Provide search functionality for GSQ staff to search for reports.

### Vendor deliverables
1.	An online lodgement portal to allow industry users to submit reports and upload associated geoscience data files in a structured, itemised format.  
    a.	Data must be able to be submitted through a human-computer interface  
    b.	Data must be able to be submitted through a computer-computer interface  
2.	A solution to allow internal GSQ users to manually enter and manage geoscience data and upload geoscience data files.
3.	Automated workflows to process the receipt, review, acceptance and rejection of geoscience data submitted to the data lake storage platform, including industry reports, industry data and internal data.
4.	A method of enabling the upload of large geoscience data files (up to low TB file size) to the data lake storage platform.

## Lodgement Portal conceptual data model


## Lodgement Portal data elements
|Data Element|Remarks|Source|
|---|---|---|
|Report number|A unique, persistent identifer|System|
|Report title|A textual name|User|
|Report description|A textual description|User|
|Report type|Lookup to controlled list of types|Vocab|
|Geoadmin feature|The features targeted in the report|Vocab|
|Earth science data category|The data categories featured in the report|Vocab|
|Commodity|The target or actual commodities featured in the report|Vocab|
|Permit|The permit number(s) covered by the report|Lookup|
|Generated by|the survey or other activity that generated the report|User|
|Attributed to|The submitter of the report<br>A lookup to controlled list of organisations|Lookup|
|Lodger|The logged-in user who lodged the report|System|
|Report period start date|The temporal coverage of the report|User|
|Report period end date|The temporal coverage of the report|User|
|Created|Date the report was lodged (date of receipt)|System|
|Issued|Date of formal issuance (open file publication)|System|
|Keywords|Terms that describe the content of the report|User|
|DOI|The Digital Object Identifier|System|
|Dataset theme|The thematic description = 'Reports'|System|
|Data access rights|Controls user and system access to the resource	|System|
|Geometry|Spatial coverage of the report|WKT|

## Lodgement Portal vocabularies
The vocabularies used in this profile are:
1. [Georesources Report Type](https://vocabs.gsq.digital/vocabulary/georesource-report)
2. [GSQ Dataset Theme](https://vocabs.gsq.digital/vocabulary/gsq-dataset-theme)
3. [Earth Science Data Category](https://vocabs.gsq.digital/vocabulary/earth-science-data-category) - the category(s) of data contained in the report
4. [Geoadmin Feature](https://vocabs.gsq.digital/vocabulary/gsq-features)
5. [Data Access Rights](https://vocabs.gsq.digital/vocabulary/data-access-rights)
6. [Commodity](https://vocabs.gsq.digital/vocabulary/gsq-commodity)

## See also
* [Industry report profile](https://github.com/geological-survey-of-queensland/industry-report-profile)

## License
This code repository's content are licensed under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/), the deed of which is stored in this repository here: [LICENSE](LICENSE).


## Contacts
*System owner*:  
**Mark Gordon**  
Geological Survey of Quensland  
Department of Natural Resources, Mines and Energy  
Brisbane, QLD, Australia  
<mark.gordon@dnrme.qld.gov.au>  

*Author*:  
**David Crosswell**  
Enterprise Architect  
Cross-Lateral Enterprises   
<https://crosslateral.com.au>
