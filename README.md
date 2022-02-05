# yet-another-Data-Analytics-Visualization-Stuff
## Data Foundation
#### Data can: 
1- information  -> meaningful eg. age is 27
2- raw data     -> have no meaning eg. (27) so is that an age , temp degre .. .. .. etc 

#### Benefits of Data: 
cheaper -> cost reduction & effeciency 
better -> gain new opp or build new product
smarter -> understand the market and customers so can make better decisions 

#### data formats 
structured  vs semi vs unstructured

#### what is database ?
less imp -> its storage where we save data into --- so why not just store it in a-file
most imp -> its a place where we collect data together to be (sharable-reliable-more secure - fast to retrieve and more .... )

#### data silos
its about the ** operational database** where accoundting db is **separate** from marketing and sales
and maybe **incompatible** too and each one has its **separate endpoint** to acess

so there is a concept of **datawarehouse** where all of this data is collected from all Rdbms and contain history of them for **BI**

#### schema
How our data is stored ?
eg. :id is pk |  age > 0 | name < 50 charachter

#### big data
volume, variety, velocity (growing so fast) and veracity(quality of it ).

#### data strategy
1-collecting data : what should we store now and what is better to store for the future | is there data we wanna scrape/buy/generate   
2-cleaning & preparing : deal with missing ,incomplete, duplicates  and wrong data
3-leverage & capitalize : how to gai value from it |  who can acess it | should we sell it/not  

#### data platform
GCP or AWS or cloudera ...etc
so here is how we evaluate who is better based on some feasures
1-**centralized authentification** (sso) sigle sign on so you sign in once to all systems you have acess to and not have to do it multiple times
2-**improved governence** better control,audit and logging 
3-**automated dashboards ** for KPIs
4-**data visualization** : charts, graphs and analyses
5-**data lake** : structred and unstructured (even not needed with no filteration)

################################################################################################################################################
## Big Data: The Big Picture
#### past vs now 
past -> trx data , keep what we need only , inclusive data (patent and closed source) , limited storage and limited scaling
now  -> behavioral , dont keep what is not needed (default to keep) , open source , cloud and limitless storage 

#### big data use cases
1-click web padge : a/b testing ,web ads and logs
2-IOT : most form of behavioral data not just trx
3-social media : tweets and posts
4-weather and sentiment analyses

#### data gravity on cloud
means the more data you move and replicate the more you pay $ and its hard to move/upload to cloud

#### MPP
![alt text](https://github.com/BillMarkEg/yet-another-Data-Analytics-Visualization-Stuff/blob/main/mpp.png)

so now dwh too has parrall processing like spark and big data tech so its so fast and use sql too.
some notes:
Hbase/kudu -> big data no-sql works in mpp as well but not sql

#### ETL 
old school: using onpremises machines
new school: Ipaas is to make a cluster on cloud 

**CDC **: capture changes(insert/updates) on DBs
**ELT **: 1- if distincation do processing better than staging tool(spark/datastage/..) 
      2- if we wanna separate data-movement & data processing (we do this of data is too large to move )
**Data Virtualization** : processing data in source without movement and can connect to many data sources (Locality processing & parrallel processing ) ex: **spark/presto**

#### data profiles
1-data scientist , 2-engineer  
3-Data steward position: ensuring the quality, including the metadata,logging ,governance and facilitate access to it  to business users so they can understand.
4-ML engineer : feature engineering, model deployment, monitor model , retrain incase of issues
5-chef data officer: Data strtegy - data culture - data management and protection

#### technologies 
Hadoop : got from GFS (Google file system)  and M/R BY #yahooooo providers =>cloudera 
Spark : berkeley lab  - in-memory  $data bricks and cloudera too

#### sql engines in big data
hive: first sql in hadoop By Facebook, phoenix : relation databse based on hbase , spark, presto , dwh
presto : by Facebook too  to solve hive and M/R issues , **do caching & mpp like dwh || don't have storage like spark just use data virtualization concept**
Kafka: **message processing**/storage system by linkedin/ then cofluent(optimized it to use sql) 
impala : mpp in hadoop

#### common dominant formats
apache arrow : columner format **in memory**
apache parquet : columner format **in disk** so **better compression ** and **easy partitioning** of data so **save cloud cost $**

#### data governance tools
apache atlas :categorize data (like cloudera navigator)
apache ranger :role authentification across big data technologies (like apache sentry in cloudera)

#### machine learning
big data give power and large cluster to tain data instead of just taining a sample  as-of limited processing power

#### cloudera vs hortonworks
cloudera -> sentry ,cloudera manager, spark , impala , kudu , parquet , kafka
hortonworks-> atlas , ranger , tez , nifi 

#### cloudera vs hortonworks Merged together !! 
![alt text](https://github.com/BillMarkEg/yet-another-Data-Analytics-Visualization-Stuff/blob/main/cloudera%20merge%20with%20hortonworks.png)

#### Data stragegy 
data is growing so fast || data in realtime like iot/sensors =>  go to big data and stream processing tools
tools : visuals/code
################################################################################################################################################
## Enterprise data management
this course consists of 3 parts

### 1-Enterprise data strategy

#### data governance
1- make data dictionary : describe the metadata ex (table describtion,dtypes,project,example)
2-naming convention:abbreviation | _ or camelcase 
3-security mangement : to have some1 from security team to know how to secure data and use encryption keys
4-make corporate grossary : defined company terminologies ex(edge,mass,flex..etc)
5-change management : document/approve/decline changes  

#### who do data governance:
non tech : 
1-CDO(chef data offecier) 
2-governance director (direct both subject matter experts + data steward)  
3-data steward (communicate with business)
tech :
1-subject matter experts( 1-  DBA +  2 -security team member) to do technical work  
2-data modeler 

#### tools
closed source : ER studio , ERWin
open source :ER one , open modelsphere

#### Data governance program 
1-standups 
2-make a CRs form for changers to fill
3-ask if the CR will affect other systems ?
4-ask requesters of change to attend meeting and communicate with other users

#### types of data
Master : data about entity  | ex: customer,hotel   | has low fill rate | the dimention in dimentional modeling
trx : eg.sales , check-in   | has high fill rate | fact tables in Dimetional modeling
lookup : to map something ex (id and name) , eg -> egypt | it is a dimention too in dimentional modeling
meta-data : data about data

#### Data Modeling (ERD)
- how masters entity connect together and make trx data
- hotel and customer to make checkin trx 
- metadata like hotelname to be string 

logical model :  physical model 
entity        -> table
attribute     -> column
row           -> record
relationship  -> pk/fk

forward engineering : to generate code(DDL scripts to create it) from physical model

### 2-managing and working with data

#### 
####

### 3-getting value from data

####
####
####
####


################################################################################################################################################
## Manageing data in the cloud

################################################################################################################################################
## principals for data quality measures

################################################################################################################################################





















