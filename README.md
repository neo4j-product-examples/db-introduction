# Introductory Demo: Using a Graph Database to Understand Connected Data

![image](https://github.com/neo4j-product-examples/db-introduction/blob/6e9dc235bb1d90fd26b2d715ea6ba2c45349cf24/img/neo4j.png)

## Prerequisites

There are two options for running the demos. The preferred approach is to use an AuraDB free account, in which you will be able to create database instances with the sample data sets already loaded. If you are using a standard AuraDB account, there is a limit of one Free instance at a time, so you will not be able to have all sample data sets available at once. Neo4j employees can request a special account that allows multiple Free instances.

The other option is to load the sample data into local databases running on Neo4j Desktop. This will allow you to have all of the databases available at once and will also allow demos where there is no connection to the Internet (provided of course, that you have already downloaded the required software and sample data first). A drawback to this option is that you will not be able to show Data Importer.

### AuraDB Option

![image](https://github.com/neo4j-product-examples/db-introduction/blob/9b8e2935c1900270c6dffa5dc281c91b6f39dc70/img/Aura.png)

For this option, simply log into your Aura account and create a Free instance. You can use any of the ptions that have sample data, but the StackOverflow, Recommendations, and Cybersecurity may resonate more. **IMPORTANT: be sure to copy and save the password somewhere. There is no way to recover it if you don't**

![image](https://github.com/neo4j-product-examples/db-introduction/blob/db82798953e370fedb277b1fd9979fdca1839c88/img/free-options.png)

Make sure to switch your account settings to workspace (and not the classic experience):

![image](https://github.com/neo4j-product-examples/db-introduction/blob/db82798953e370fedb277b1fd9979fdca1839c88/img/workspace-options.png)

### Local (Neo4j Desktop) Option

First, download and install [Neo4j Desktop](https://neo4j.com/download/). Open Neo4j Desktop and click the graph apps icon on the left. Insure that you have Neo4j Browser and Neo4j Bloom installed:

![image](https://github.com/neo4j-product-examples/db-introduction/blob/db82798953e370fedb277b1fd9979fdca1839c88/img/graph-apps.png)

Follow these steps:

- Create a new project
- Add one (or more) of the dump files containing the sample data set(s)
- Use the context menu to create a new DBMS from the dump file. Alternatively, if you already have an instance (DBMS) running, you can import dump into existing dbms
- In most cases, you should use the latest version of Neo4j
- Click the "start" button next to the new DBMS. Depending on your OS and what services are running, you may be prompted to fix the configuration because of port conflicts
- test by opening the dbms using browser and running this query: `call db.schema.visualization` You should see a representation of the schema (you may have to click the "graph" view)
- test by opening the dbms with bloom and running `show me a graph` 
- Default memory setup should be sufficient for simple demos, but you can increase if you like