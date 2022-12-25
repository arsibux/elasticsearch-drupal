# Elasticearch-drupal
elasticsearch with drupal 8


## TASK: Optimize the search Performance

Currently the system is using drupal internal database search and providing custom rest API that fetching data from drupal linked database.
Challenge: Implementation of All search related drupal exposed rReSTful APIs with elasticsearch service.

## SYSTEM SPECIFICATIONS:

** DRUPAL:8.9.13 as BACKEDN CMS Exposing ReSTful APIs.
** Mariadb: 10.4
** ANGULAR:        as FRONTEND Client.
** SEARCH: Drupal is using Internal DATABASE SEARCH { Custom API for fetching data from database }

# DEPENDENCIES:
  * Elastissearch Service
  * Elasticseacrch Connector Drupal contrib module
  * Search API Drupal core module.
  * Views core module.
  * Webservices drupal core modules.

* Elastic Search Setup can be achieved by following two ways.

    1. Setup Elasticsearch Server at seperate VM  or install. For connection b/w drupal and elasticsearch, drupal provides a contrib module {elasticsearch_connector} which establish connection. https://www.drupal.org/project/elasticsearch_connector

    Note:This project is not covered by Drupal’s security advisory policy.
    but 5,161 sites report using this module

   2. Cloud based Service
      * elastic.co[https://www.elastic.co/cloud/]

      * AWS (https://aws.amazon.com/marketplace/pp/prodview-voru33wi6xs7k)
        for connection https://www.drupal.org/project/elasticsearch_aws_connector.

        Note:This project is not covered by Drupal’s security advisory policy.
    but 353 sites report using this module sites report using this module.

After enabling {elasticsearch_connector and search_api modules}

1. Establish connection between DRUPAL CMS and ELASTICSEARCH by using UI fo elasticsearch_connector.

2. Configur search_api with elasticsearch.

3. Add index and configur datasource by selecting  entity and its fields for elasticsearch server.

4.




ES
NASA SCIENCE
https://science.nasa.gov/
drupal + elasticsearch_connector
USGS STORE
https://store.usgs.gov/




## RESOURCES
https://www.youtube.com/watch?v=_h12KHPg_WE

https://opendistro.github.io/for-elasticsearch-docs/docs/elasticsearch/ux/
https://medium.com/quantyca/reviving-an-e-commerce-search-engine-using-elasticsearch-e540751c6d99
https://www.youtube.com/watch?v=K-DWcM886Z4

https://www.youtube.com/watch?v=_h12KHPg_WE
https://www.youtube.com/watch?v=OoMZPU4EGrU
https://www.youtube.com/watch?v=FkxAfpvRrbc

### RANGE QUERIES
https://linuxhint.com/elasticsearch-range-query/

### SPELLCHECK FUZZINESS
  https://engineering.empathy.co/spellcheck-in-elasticsearch/

### AUTOCOMPLETE
  https://opster.com/guides/elasticsearch/how-tos/elasticsearch-auto-complete-guide/
