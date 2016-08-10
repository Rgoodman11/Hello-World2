progress report - EDSA Demand Analysis Dashboard

Contributing Partners [OU / Fraunhofer / JSI]

Summary of Work Done - 02-07.2006
	- data update - increased coverage across EU
	- design & UI update - now employs three main task-based views each containing multiple components


Developers meeting held Mar 08-10, hosted by JSI



[DETAIL]

***Design Review***

The current version of the dashboard (on the EDSA website [4] - updated end Jun 2016) is based on a full user interface (UI) and system design review, carried out during the Mar 2016 developers meeting in Ljubljana. The new UI design sketches are available at [1]. 
Key changes are to present data and (three main) views based on core user tasks for three key users: the policy maker, the job seeker and the Data Science practitioner or expert.

All views make use of a common data set, and some components are reused across views. The design encourages independent construction of components, to increase reusability and extensibility, and to allow contributions from different partners. The "integrated" dashboard will however provide transparent coupling of components within and across views. This task is on-going; the current version of the dashboard (Jun 2016) provides access to all views from a single location but with direct coupling only between components in a single view.



*** Job Demand Data & RDF Store ***

* Data extracted from Nov 2015
	- total count after completion of the data acquisition and enrichment process - 316,841.

Validation of the results of data acquisition is based on the EDSA Skills and JobPosting ontology (Saro) and a set of pre-specified criteria, such as the requirements for a job posting date and match to a location specified in the GeoNames database. Validated data encoded as RDF should also be set to type edsa:JobPosting.
	
	- validated job posting entries - 308,528
	- all data extracted from Aug 2015, including also otherwise validated job postings, but not annotated as type edsa:JobPosting - 318,579.

* Coverage end Jun 2016 - 22 EU and 5 EEA countries


*** Skill extraction ***
	- post Nov 2015 the process employs the JSI data acquisition pipeline. Skills relevant to Data Science are extracted from the input data based on concepts defined in DBpedia [7]. The pipeline employs automatic annotation, but with the option for manual correction. Where required for data analysis and presentation on the dashboard, manual mapping to the named (WP1) EDSA skills and skill sets is carried out on the input data.



*** Development ***

Redevelopment of map view - a number of limitations in the original visualisation and data processing libraries prevented detailed map views beyond a very low threshold (around 10K entries). The map-based view has therefore been rebuilt; a single layout built for the policy maker view is reused in the job seeker view. Statistical charts directly coupled to the map view provide extra detail for selected data attributes - time (posting date); location (city & country); skills (a superset of the named EDSA skills). 

To satisfy the requirement for linking the results of demand analysis to corresponding courses the prototype currently searches for related learning material based on (exact) keyword match to skills in the result set of a user query. Extension to semantic search is on-going. Currently this task extracts results from a single resource - the JSI VideoLectures repository [8].


The skillset viewer (employing parallel coordinates) has been updated to display (aggregated) views for the much larger dataset. The layout groups data by default by location (country or city), with level of detail (aggregated) by time (week, month or year). The highest level of detail shows individual postings (for a filtered result set) - currently only in table form.



*** Update of EDSA Website ***

The most recent update was completed end June 2016. This version was demoed at EDF 2016. End users also now have access to a public SPARQL endpoint; sample queries are available from the Dashboard. The component and input data descriptions (including that of the supply data analysis) have also been updated.



*** Other Related Work ***

Initial analysis of the idexLab expertise dataset is on-going. This will feed into skills analysis and the practitioner view in the Dashboard.



References

[1] Design Sketches, Mar 2016: https://drive.google.com/drive/folders/0B0_hDP5ZEqKbWDZONDFvYmE3eVk?ths=true
[2] Other design & development documents: https://drive.google.com/drive/folders/0B0_hDP5ZEqKbMzRqdzlEOC0zcms?ths=true
[3] SPARQL endpoint: http://dashboard.edsa-project.eu:3030
[4] EDSA Demand Analysis Dashboard: http://edsa-project.eu/resources/dashboard
[5] Saro - http://eis.iai.uni-bonn.de/Projects/SARO.html, http://eis.iai.uni-bonn.de/vocab/saro/
[6] GeoNames Database: http://geonames.org
[7] DBpedia: http://wiki.dbpedia.org
[8] VideoLectures.NET: http://videolectures.net/
