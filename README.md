#Tasks

##Steps
* Spin up ec2 instances, weekly, monthly, etc. 
* Run download scripts
  * OSM
  * Who's on First
* Push data into PostgreSQL (PostGIS enabled) via psycopg2
* Run geoprocessing scripts OSM against Who's on First gazateer (intersect)
* Do some basic descriptive statistics (in Pandas or with Python-SQL wrapper)
* Push stats out to files (csv or json)
* Script to generate website (html, js, etc.)
* Site hosted on github.io site, using d3, generate graphics and charts

##Description
* Something that “rolls up” stats by Who’s On First neighbourhoods, city, county, state, country, and globally about data in OSM or other sources. 
* That presents that in a generated website with "pages" for each of those features and their individual roll up, with an eye towards trends and projections. 
* Updates itself on some cadence, say weekly, so the data doesn’t go stale. Something that leverages AWS infrastructure to do some of the heavy lifting. 

##AWS Notes
44 GB's about global. update at dif. points, and do some basic geoprocessing
* How can I script up spinning up ec2 instances?
  * [AWS Python SDK](https://aws.amazon.com/developers/getting-started/python/)    

* Can I force them to run the download and CREATE TABLE OR INTERSECT scripts? 
* Should I leave my RDS instances up and running or should I export them and save them on S3?
  * Fuck no!
  
* RDS snapshots will be stored on s3, but access them RDS console.


