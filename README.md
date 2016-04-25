# LazyWebCypher

LazyWebCypher is a simple way to execute multi-statement Cypher scripts (the kind with semicolons, ;) from the web. Currently the Neo4j Browser does not support this, so this is a lazy person's workaround...

Are you lazy? Do you write Cypher statements? Often multiple statement scripts that do things like `CREATE INDEX`es and `LOAD CSV` files? Then LazyWebCypher is for you.

## What is it?

A simple web app that facilitates executing loading and executing multiple statement Cypher scripts (the kind with semicolons) against a running instance of Neo4j, either local or a remote server.

## Why do I need it?

You probably don't, however...

Often during an initial data import you want to execute a multiple statement Cypher script, usually with `CREATE INDEX` and`LOAD CSV` statments. Currently the Neo4j browser does not support executing multiple statement Cypher queries so you can either cut and paste your statements one at time or use something like `neo4j-shell`. But if you're lazy, you're not gonna do that, you're gonna use LazyWebCypher!

## What can it do?

LazyWebCypher does two things:

1. Load Cypher files (from a quey param, local file, remote url, or manual editing)
1. Execute multiple statement Cypher queries against a running Neo4j instnace

### Load Cypher files

#### Load Cypher files with a query parameter

Like this: [http://johnymontana.github.io/LazyWebCypher/?file=https://raw.githubusercontent.com/legis-graph/legis-graph/master/quickstart/114/legis_graph_import_114.cypher](http://johnymontana.github.io/LazyWebCypher/?file=https://raw.githubusercontent.com/legis-graph/legis-graph/master/quickstart/114/legis_graph_import_114.cypher)

#### Load local Cypher files 

#### Load Cypher script from remote URL

### Execute Cypher scripts

Simply supply the connection url (and optionally Username/Password credentials) for an existing Neo4j instance and your queries will be executed directly from the browser, one at a time. Note that each statement is executed in its own transaction, this serves two purposes:

1. `CREATE INDEX` or `CREATE CONSTRAINT` statements need to be executed in a separate transaction
1. Better support for data import `LOAD CSV` Cypher statements by breaking your script up into multiple transactions


**What are some examples that I can use with LazyWebCypher?**

Submit an issue or PR to add yours!

* [FEC Filings 2015](http://johnymontana.github.io/LazyWebCypher?file=https://gist.githubusercontent.com/johnymontana/fd3de5219e9a15e67fb7/raw/7f25d1f2b37a1811720b1d3339335a60b7c6e35f/FEC-2015.cql)
* [legis-graph: US Congress in a Graph](http://johnymontana.github.io/LazyWebCypher/?file=https://raw.githubusercontent.com/legis-graph/legis-graph/master/quickstart/114/legis_graph_import_114.cypher)

## Think this is lame?

Tell me about it [@lyonwj](https://twitter.com/lyonwj)
