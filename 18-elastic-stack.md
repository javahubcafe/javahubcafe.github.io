Elasticsearch
What is Elasticsearch?
Elasticsearch is the living heart of what is today the world’s most popular log analytics platform — the ELK Stack (Elasticsearch, Logstash, and Kibana). The role played by Elasticsearch is so central that it has become synonymous with the name of the stack itself. Used primarily for search and log analysis, Elasticsearch is today one of the most popular database systems available today.

Initially released in 2010, Elasticsearch is a modern search and analytics engine which is based on Apache Lucene. Completely open source and built with Java, Elasticsearch is categorized as a NoSQL database. Elasticsearch stores data in an unstructured way, and up until recently you could not query the data using SQL. The new Elasticsearch SQL project will allow using SQL statements to interact with the data. You can read more on that in this article.

Unlike most NoSQL databases, though, Elasticsearch has a strong focus on search capabilities and features — so much so, in fact, that the easiest way to get data from Elasticsearch is to search for it using its extensive REST API.

In the context of data analysis, Elasticsearch is used together with the other components in the ELK Stack, Logstash and Kibana, and plays the role of data indexing and storage.

Read more about installing and using Elasticsearch in our Elasticsearch tutorial.

Basic Elasticsearch Concepts
Elasticsearch is a feature-rich and complex system. Detailing and drilling down into each of its nuts and bolts is impossible. However, there are some basic concepts and terms that all Elasticsearch users should learn and become familiar with. Below are the six “must-know” concepts to start with.

Index
Elasticsearch Indices are logical partitions of documents and can be compared to a database in the world of relational databases.

Continuing our e-commerce app example, you could have one index containing all of the data related to the products and another with all of the data related to the customers.

You can have as many indices defined in Elasticsearch as you want but this can affect performance. These, in turn, will hold documents that are unique to each index.

Indices are identified by lowercase names that are used when performing various actions (such as searching and deleting) against the documents that are inside each index.

Documents
Documents are JSON objects that are stored within an Elasticsearch index and are considered the base unit of storage. In the world of relational databases, documents can be compared to a row in a table.

In the example of our e-commerce app, you could have one document per product or one document per order. There is no limit to how many documents you can store in a particular index.

Data in documents is defined with fields comprised of keys and values. A key is the name of the field, and a value can be an item of many different types such as a string, a number, a boolean expression, another object, or an array of values.

Documents also contain reserved fields that constitute the document metadata such as _index, _type and _id.

Types
Elasticsearch types are used within documents to subdivide similar types of data wherein each type represents a unique class of documents. Types consist of a name and a mapping (see below) and are used by adding the _type field. This field can then be used for filtering when querying a specific type.

Types are gradually being removed from Elasticsearch. Starting with Elasticsearch 6, indices can have only one mapping type. Starting in version 7.x, specifying types in requests is deprecated. Starting in version 8.x, specifying types in requests will no longer be supported.

Mapping
Like a schema in the world of relational databases, mapping defines the different types that reside within an index. It defines the fields for documents of a specific type — the data type (such as string and integer) and how the fields should be indexed and stored in Elasticsearch.

A mapping can be defined explicitly or generated automatically when a document is indexed using templates. (Templates include settings and mappings that can be applied automatically to a new index.)

Shards
Index size is a common cause of Elasticsearch crashes. Since there is no limit to how many documents you can store on each index, an index may take up an amount of disk space that exceeds the limits of the hosting server. As soon as an index approaches this limit, indexing will begin to fail.

One way to counter this problem is to split up indices horizontally into pieces called shards. This allows you to distribute operations across shards and nodes to improve performance. You can control the amount of shards per index and host these “index-like” shards on any node in your Elasticsearch cluster.

Replicas
To allow you to easily recover from system failures such as unexpected downtime or network issues, Elasticsearch allows users to make copies of shards called replicas. Because replicas were designed to ensure high availability, they are not allocated on the same node as the shard they are copied from.  Similar to shards, the number of replicas can be defined when creating the index but also altered at a later stage.

For more information on these terms and additional Elasticsearch concepts, read the 10 Elasticsearch Concepts You Need To Learn article.

Elasticsearch Queries
Elasticsearch is built on top of Apache Lucene and exposes Lucene’s query syntax. Getting acquainted with the syntax and its various operators will go a long way in helping you query Elasticsearch.

Boolean Operators
As with most computer languages, Elasticsearch supports the AND, OR, and NOT operators:

jack AND jill — Will return events that contain both jack and jill
ahab NOT moby — Will return events that contain ahab but not moby
tom OR jerry — Will return events that contain tom or jerry, or both
Fields
You might be looking for events where a specific field contains certain terms. You specify that as follows:

name:”Ned Stark”
Ranges
You can search for fields within a specific range, using square brackets for inclusive range searches and curly braces for exclusive range searches:

age:[3 TO 10] — Will return events with age between 3 and 10
price:{100 TO 400} — Will return events with prices between 101 and 399
name:[Adam TO Ziggy] — Will return names between and including Adam and Ziggy
Wildcards, Regexes and Fuzzy Searching
A search would not be a search without the wildcards. You can use the * character for multiple character wildcards or the ? character for single character wildcards.

URI Search
The easiest way to search your Elasticsearch cluster is through URI search. You can pass a simple query to Elasticsearch using the q query parameter. The following query will search your whole cluster for documents with a name field equal to “travis”:

curl “localhost:9200/_search?q=name:travis”
Combined with the Lucene syntax, you can build quite impressive searches. Usually, you’ll have to URL-encode characters such as spaces (it’s been omitted in these examples for clarity):

curl “localhost:9200/_search?q=name:john~1 AND (age:[30 TO 40} OR surname:K*) AND -city”
A number of options are available that allow you to customize the URI search, specifically in terms of which analyzer to use (analyzer), whether the query should be fault-tolerant (lenient), and whether an explanation of the scoring should be provided (explain).

Although the URI search is a simple and efficient way to query your cluster, you’ll quickly find that it doesn’t support all of the features offered to you by Elasticsearch. The full power of Elasticsearch is exposed through Request Body Search. Using Request Body Search allows you to build a complex search request using various elements and query clauses that will match, filter, and order as well as manipulate documents based on multiple criteria.

More information on Request Body Search in Elasticsearch, Query DSLand examples can be found in our: Elasticsearch Queries: A Thorough Guide.

Elasticsearch REST API
One of the great things about Elasticsearch is its extensive REST API which allows you to integrate, manage and query the indexed data in countless different ways. Examples of using this API to integrate with Elasticsearch data are abundant, spanning different companies and use cases.

Interacting with the API is easy — you can use any HTTP client but Kibana comes with a built-in tool called Console which can be used for this purpose.


As extensive as Elasticsearch REST APIs are, there is a learning curve. To get started, read the API conventions, learn about the different options that can be applied to the calls, how to construct the APIs and how to filter responses. A good thing to remember is that some APIs change and get deprecated from version to version, and it’s a good best practice to keep tabs on breaking changes.

Below are some of the most common Elasticsearch API categories worth researching. Usage examples are available in the Elasticsearch API 101 article. Of course, Elasticsearch official documentation is an important resource as well.

Elasticsearch Document API
This category of APIs is used for handling documents in Elasticsearch. Using these APIs, for example, you can create documents in an index, update them, move them to another index, or remove them.

Elasticsearch Search API
As its name implies, these API calls can be used to query indexed data for specific information. Search APIs can be applied globally, across all available indices and types, or more specifically within an index. Responses will contain matches to the specific query.

Elasticsearch Indices API
This type of Elasticsearch API allows users to manage indices, mappings, and templates. For example, you can use this API to create or delete a new index, check if a specific index exists or not, and define a new mapping for an index.

Elasticsearch Cluster API
These are cluster-specific API calls that allow you to manage and monitor your Elasticsearch cluster. Most of the APIs allow you to define which Elasticsearch node to call using either the internal node ID, its name or its address.

Elasticsearch Plugins
Elasticsearch plugins are used to extend the basic Elasticsearch functionality in various, specific ways. There are plugins, for example, that add security functionality, discovery mechanisms, and analysis capabilities to Elasticsearch.

Regardless of what functionalities they add, Elasticsearch plugins belong to either of the following two categories: core plugins or community plugins. The former is supplied as part of the Elasticsearch package and are maintained by the Elastic team while the latter is developed by the community and are thus separate entities with their own versioning and development cycles.

Plugin Categories
API Extension
Alerting
Analysis
Discovery
Ingest
Management
Mapper
Security
Snapshot/Restore
Store
Installing Elasticsearch Plugins
Installing core plugins is simple and is done using a plugin manager. In the example below, I’m going to install the EC2 Discovery plugin. This plugin queries the AWS API for a list of EC2 instances based on parameters that you define in the plugin settings :

cd /usr/share/elasticsearch sudo bin/elasticsearch-plugin install discovery-ec2
Copy
Plugins must be installed on every node in the cluster, and each node must be restarted after installation.

To remove a plugin, use:

sudo bin/elasticsearch-plugin remove discovery-ec2
Copy
Community plugins are a bit different as each of them has different installation instructions.
