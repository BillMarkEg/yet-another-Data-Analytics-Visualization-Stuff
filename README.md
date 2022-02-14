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
Embedded SQl : quering tables directly from ur backend-application (network-load) 
storeed procedure : is better (separate app from db) (no network load) (more data encapulation) (safe from sQl ingesions attacks)

data compliance audit:
database acess ::
1-store failed login attempts 
2-change management records : if usr needs to change anything
3-principal of least previleges : to give each user minumum previligies to get his task done

subject data ::
4-appreperiate types of data (foreg. date is date not ts or sting)
5-data retention
6-who can acess and how its secured ?

### 3-getting value from data

Data engineer:collect data 
bi :  finds patterns - what if ? (past analyses) (sql + bi tools like tabeau)
data Scientist : (sampling/hyposesis/A/b testing/predictions) 

**predictions** 
supervied algo (tain/test datasets are available): decision trees | naive bayes | regression | svm
non-supervied algo tain only datasets are available: clustering(kmeans/knn) | anomaly detection

tools for algorithms: python(scikit-learn/tensorflow) -- R(caret)
visualization :  ex:matplot lib / or use tools like tableau

################################################################################################################################################
## Manageing data in the cloud
#### phases
1-Create: get data and classify (critical/normal data for security)
2-store: where to store & how  |  encryption | tokenization(splitting) | data Masking: fake copy of data for testing | digital right management : like copywrites so prevent                                                                                                                                                       users from editing ur content
3-use : 
            - if there is modification so its in creation phases so it requires reClassification
            - most vulnerable : may include movement of data to insecure storage 
            - decryption for procession 
           
4-share 
5-archive  : data become cold
6-destroy  : data is removed from cloud

#### control examples
Control : allow/prevent actions
![alt text](https://github.com/BillMarkEg/yet-another-Data-Analytics-Visualization-Stuff/blob/main/control%20examples.png)

#### Data Classification
1-Data Type
2-Contrains 
3-ownership
4-retention
5-business constains
6-encryption

#### Data reClassification
1-Data Transformation (reCheck classification of Data) ex moving data from raw to business scehma 
2-Data Movement to another platform (reCheck classification of Data) ex moving data from test (bde)  schema to production ex  ds schema  so encryption is needed (reClassification)

#### Cloud storage architecture
**IAAS** (you ctr os and every thing on in )
1-ephemeral : exists only while VM is running
2-volume : like local hard disk (folders and files ) we can use for rdbms or OS or anything just like hard-disk
3-object/blob : used for large files (all data stored with same level with id so fast access to data )
4-raw : 
5-long term : for data archiving 

**PAAS** (you ctr app and data)
1-Relation db 
2-key value pair : like Hbase
3-Map reduce : model that process data in chunks

**SAAS** (ex google drive)
1-information storage and management : ui to acess data
2-content/file storage : use volume or object for storing files on cloud
3-CDN(content deleivery Network) : data is stored and replicated in different regions so its fast to retrieve.

#### Data replication
Strict : data is replicated on all nodes but only portion % of it is avail for read/write then rest is synced (fast/no overhead) 
eventual : data is replicated on all nodes and all is avail for read/write (extreme fast / overhead in syncing )

#### storage threads
1-Data breaches : data movement to public (like what happedn in hooliwood)
2-week identy and acess mng : week password or writing password in code and upload it to github
3-insecure api : give api to others and it contains bugs they can acess other data or attach 
4-system vulnerabilities : in os itself like windows or linux issues 
5-accound hijack : login with ur password (may get it through phishing like face(p)book app)
6-malicious insider attach : attach comes from members inside 
7-Dos : hard-drive - memory can't work due to attach 
8-Ddos : distributed dos
9-spoofing identy : normail log using ur password and uname 
10-tampering with data : modification of data you have 

#### State of data
in motion : currently being accessed or transferred from host to another (downloaded - usb move - ftb)
in rest   : data not moved : ex archived 
in use    :  is data that is currently being updated, processed, accessed and read by a system

#### encryption in data:
raw level : by cloud provider when data is loaded imported/exprted from it
storage level : 
                  1-instance : exist on volume/object/application(of database)/file storage itself
                  2-proxy : there is another machine that ctr encryption of data
                  
#### Data masking : 
1-static : just once we do it manually change the data for testing
2-dynamic : a layer exists on production between client and database to change data dynamiclly through : 
                                                                                                    1- random substitution
                                                                                                    2- algorithmetic substitution
                                                                                                    3-shuffle data together
                                                                                                    4-masking (substitution only **part** of the data)
                                                                                                    5-deletion of specific **part** of the data
#### Data anonimization :
1-direct : data that identify the user like msisdn/name
2-indirect : data that can match together to identify user indirectly
so we **encrypt** them all.

#### Data Tokenization : 
tokenization uses a token to protect the data,
whereas encryption uses a key.
tokenization **swaps** sensitive data for an irreversible, nonsensitive placeholder (token) and securely stores the original, sensitive data **outside** of its original environment, and encryption **encodes the content** of a data element where it resides with a key shared between whoever is encrypting the data and whoever need to decrypt it.

#### Data leakage protection (DLP) :
ctr what data end user can transfere/download to avoid data loss or data leakage

#### data security:
consists of 1-confidenciality : least preveligies granted for user to do his task on data
            2- availability : data avail 24/7
            3- integrity : data is the same and prevent unauthorized changes
#### Data roles
subject : the subject of data 
controller : who define why we collect data how it will be processed and by who 
processer : who work on it 
steward : who maitain data governance on data & define business rules
data custodian : who technically store and maintain data (ex: DBA)
data owner : who own the data 

#### pii (identity data that should be secured)
FullName(should be full)-adress-email-id-passport-vechleNum-DOB-birthplace-msisdn-creditCard-fingerprint-handwriting-face-loginName-passwords

#### DRM (data right Mng)
1-Acl (read/write/excute)
2-integration with mail server
3-prevent print document/screenshots/copt-paste/page watermarking 

autorization : can he acess or not , it can be : 
1-sigle factor: just password
2-multifactor : password + RSA + ensure not robot and more..

authentication : what can you do (ACL)

#### cold data
1-retention --> 2-archiving --> 3-deletion
we should **keep logs monitored** on who use data and data modification

################################################################################################################################################
## principals for data quality measures

#### ML 
<br> supervised : labels
<br> unsupervised : no labels | find relationships between data
<br> semi supervised : fiew labels as it tries to use all data
<br> reEnforcement : learn from feedback and reward system 

#### Feature Engineering
<br> imputation : nulls and missing 
<br> handling outliers
<br> binning 
<br> log transform
<br> once hot encoding
<br> grouping operations 
<br> Scaling

#### Data Quality metrics
1- ratio of data to error \
2- ratio of nulls \
3- data transformations errors eg.float/decimal in RM \ 
4- amount of dark data : use profiling & data discovery to understand it \

################################################################################################################################################





















