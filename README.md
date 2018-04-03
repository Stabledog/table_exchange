#  Data Table Exchange 


## Background

The task of copying data tables from one representation to another -- and filtering the data in transit -- is an endless swamp of disjoint tools and technologies. 

Database connectors, data-read techniques, file format and schema proliferation, SQL joins, HTML conversion and rendering, Unix piping tools... the set of details one must understand and track just to copy and filter a table from one place to another can be mind-numbing.

This tool tries to put out some of the fire by lighting another match -- yet another tool.  But to unify the bits of this problem, DataTableExchange identifies common tasks, patterns, and flows and provides a framework which offers to organize most of it.

## Problem structure
At the most abstract level, we're trying to solve just a few common problems:

- Ingestion: reading a data table

- Filtering: selecting or altering data in transit after injestion

- Export: outputting the results into a desired storage location and format.

- Configuration: keeping track of the metadata needed to repeat the job, and providing understandable idioms for maintaining and creating configurations.

- I/O generalization: decoupling the I/O mechanisms from the other parts of the problem to allow for flexibility.

## Goals

- Simplify the creation and maintenance of I/O abstractions ("comdb2 extractor", ".csv extractor", "html renderer", etc.)

- Flexible and uniform filtering rules: allow the user to define rules to be applied for selection and transformation in transit

- Be portable: use Python.

- Be scaleable: don't limit the size of the table -- stream, filter, and store in a continuous flow whenever possible.

- Be robust: don't break. Handle exceptions intelligently.


