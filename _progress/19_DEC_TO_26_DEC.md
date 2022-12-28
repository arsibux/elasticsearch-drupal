
## DEMONSTRATION
Integration of ES with Zain Eshop { Drupal 8 CMS }

WORK PROGRESS 19-DEC-2022 - 28-DEC-2022

**STEPS**

- [V] Web Development Stack is up and running.
- [V] Modules {Elasticsearch Connector and Search API} are enabled.
- [V] Connection b/w ES and D8 CMS is established.
- [V] Drupal exposed API { ReST API for Fulltext seach }
- [V] API Testing Postman { https://zaineshop.ddev.site/products/v1/_search?text=sim }

**FULLTEXT SEARCH**
Searching keyword{ text } in all text type fields of the entity{ product }.
Title field search is implemented so far. We can add other text type fields on requirement.

**USE CASES**

- without any keyword -> Display all records 489
- with keyword -> Filtered records on condition keyword match in title field.
