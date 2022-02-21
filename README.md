## REDTab

This repository hosts the REDTab dataset, the largest natural-table relation extraction dataset. In our dataset, we have a total of 9,149 tables, and 22,236 column pairs from Music and Literature domains. We release two categories of REDTab:

 - REDTab-standard: This is the standard REDTab which includes 23 different relations.
 - REDTab-simple: This is a filtered version which only focuses on the top 10 most popular relations.

### Data Format

#### Table Format

The table data can be found in `Tables` folder. The tables in this dataset are in .json format and taken from WDC web-tables (http://webdatacommons.org/). 

#### Annotation Format

The annotated data can be found in `REDTab-standard` or `REDTab-simple`, depending on the category. In each folder, the data is in .csv format, divided into train and test split. 

Each row represents a column-pair relation annotation in a format of:
```
Left, Relation, Right, L_id, R_id, Table
```

`Left`: contains the header for one of the column in the column pair. It is called 'Left' because the header is placed to the left of the relation name.  
`Relation`: contains the annotated relation between the column pair.  
`Right`: contains the header for one of the column in the column pair. It is called 'Right' because the header is placed to the right of the relation name.  
`L_id`: The index of the `Left` column header in the table.  
`R_id`: The index of the `Right` column header in the table.  
`Table`: The filename of the table. The {filename}.json can be found in Tables/ folder  

Note: Either one of the `L_id` or `R_id` is the index of the main column which be referred in `keyColumnIndex` in the table file present in Tables/ folder.


For example:

```
Author, is the author of, Attachment Name, 5, 1, 6c1f39b3-b060-4970-81ec-5a15c7c71583.json
```

This row explains that in a table from `Tables/6c1f39b3-b060-4970-81ec-5a15c7c71583.json`, the 5th column (header name is Author) is the author of the 1st column (header name is Attachment Name).

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This project is licensed under the CC-BY-4.0 License.

The web tables are a structured set of data made up of rows and columns, and come from largest corpora of relational Web tables from the Common Crawl which is available for public download, called Web Data Commons or WDC (http://webdatacommons.org/webtables/). We randomly sampled part of the dataset, extracted all the column headers, and chose relations that were useful in Music and Literature domain of web-tables. According to WDC, the web tables in its corpora are derived from Common Crawl (http://commoncrawl.org/). The web tables in REDTab are provided “as is” for the user’s convenience. Amazon has no license rights in, or ownership of, the web tables in REDTab. 

The annotations in REDTab are human-annotated, high quality relations that connect column pairs in a table, and are licensed under a Creative Commons Attribution 4.0 International License (https://creativecommons.org/licenses/by/4.0/). 
