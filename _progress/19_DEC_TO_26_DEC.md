WORK PROGRESS 19-DEC-2022 - 26-DE-2022

TASK: Integration of ES with Zain Eshop { Drupal 8 CMS }

REQUIREMENT

[] Web Development Stack is up and running.
[] Modules {Elasticsearch Connector and Search API} are enabled.
[] Config elasticsearch_connector with Elasticsearch Server.
[] Connection b/w ES and D8 CMS is established.
[] Config search_api and index for entity and fields.
[] Drupal View { ReST API for Fulltext seach }
[] API Testing Postman { https://zaineshop.ddev.site/products/v1/_search?text=sim }

FULLTEXT SEARCH
Searching keyword{ text } in all text type fields of the entity{ product }.
Title field search is implemented so far. We can add other text type fields on requirement.

USE CASES

- without any keyword -> Display all records
- with keyword -> Filtered records on condition keyword match in title field.

