# Elastiscearch Drupal 8

Elasticsearch integration with Drupal 8 CMS using core module SEARCH API and features contrib modules Elasticsearch  Connector.

### SEARCH PERFORMANCE OPTIMIZATION

  Currently the system is using drupal internal database search and providing custom rest API that fetching data from drupal linked database.
  Challenge: Implementation of All search related drupal exposed rReSTful APIs with elasticsearch service.

### SYSTEM SPECIFICATIONS

  * DRUPAL:8.9.13 as BACKEDN CMS Exposing ReSTful APIs.
  * Mariadb: 10.4
  * ANGULAR: as FRONTEND Client.
  * SEARCH: Drupal is using Internal DATABASE SEARCH { Custom API for fetching data from database }

## METHOD 1 {Using core and contrib Drupal modules }

  ### DEPENDENCIES

    * Elastissearch Service
    * Elasticseacrch Connector Drupal contrib module
    * Search API Drupal core module.
    * Views core module.
    * Webservices drupal core modules.

  ### ES INTEGRATION WITH D8 CMS

  Elastic Search Setup can be achieved by following two ways.
    1. Setup Elasticsearch Server at seperate VM  or install. For connection b/w  drupal and elasticsearch, drupal provides a contrib module {elasticsearch_connector} which establish connection. https://www.drupal.org/project/elasticsearch_connector

    Note:This project is not covered by Drupal’s security advisory policy.
    but 5,161 sites report using this module

    2. Cloud based Service
      * elastic.co[https://www.elastic.co/cloud/]
      * AWS (https://aws.amazon.com/marketplace/pp/prodview-voru33wi6xs7k)
        for connection https://www.drupal.org/project/elasticsearch_aws_connector.

    Note:This project is not covered by Drupal’s security advisory policy.
    but 353 sites report using this module sites report using this module.

  After enabling {elasticsearch_connector and search_api modules}

  ### DRUPAL MODULES INSTALLATION AND CONFIGURATION

    1. Search API enable and elasticearch_connector downlaod via composer and enabled
    2. Establish connection between DRUPAL CMS and ELASTICSEARCH by using UI fo elasticsearch_connector.
    3. Configur search_api with elasticsearch.
    4. Creating index {idx_product} product in Search API.
    5. Configur datasource by selecting  entity {PRODUCT} and its fields for elasticsearch server.
    6. Create View {Rest Export Page with path} and select index as content.


## METHOD 2 { Custom Development }

  ### NEW MODULE {zain_elasticsearch}

  ### SEARCHING APIs IN KIBANA

    * List of Indices in elasticsearch

    `GET /_cat/indices?v`

    * Get all doc product idx
    ```
    GET elasticsearch_index_db_idx_product/_search
    {
      "query":{
        "match_all": {
        }
      }
    }
    ```

    * Get all indices in elasticsearch ***
    ```
    GET /elasticsearch_index_db_idx_product/_search
    {
      "query":{
        "match": {
          "status": false
        }
      }
    }
    ```

    * Fulltext

    * Autocomplete
    ```
    GET /elasticsearch_index_db_idx_product/_search
    {
        "query": {
            "match": {
                "title": {
                    "query": "raider "
                }
            }
        }
    }
    ```

    * Setting for search as you type
    ```
    PUT elasticsearch_index_db_idx_product
    {
      "mappings": {
        "properties": {
          "title": {
            "type": "search_as_you_type"
          }
        }
      }
    }
    ```
    * Search
    ```
    GET elasticsearch_index_db_idx_product/_search
    {
      "query": {
        "multi_match": {
          "query": "reider ",
          "type": "bool_prefix",
          "fields": [
            "title",
            "title._2gram",
            "title._3gram"
          ]
        }
      }
    }
    ```

    * Spellcheck Fuzziness
    ```
    GET /elasticsearch_index_db_idx_product/_search
      {
      "suggest": {
        "text": "reid",
        "spellcheck-term": {
          "term": {
            "field": "title"
          }
        },
        "spellcheck-phrase": {
          "phrase": {
            "field": "title"
          }
        }
      }
    }
    ```

    * Range
    ```
    GET /elasticsearch_index_db_idx_product/_search
    {
      "query": {
        "range": {
          "product_id": {
            "gte": 1000,
            "lte": 2000
          }
        }
      }
    }
    ```

    * Semantic

  ### EXAMPLES

  * [NASA SCIENCE](https://science.nasa.gov/) Drupal + Elasticsearch
  * [USGS STORE](https://store.usgs.gov/)

## REFERENCES

  * [ES integration with Drupal CMS](https://www.lullabot.com/articles/indexing-content-from-drupal-8-to-elasticsearch)
  <!-- * [Video](https://opendistro.github.io/for-elasticsearch-docs/docs/elasticsearch/ux/)
  * [Video](https://medium.com/quantyca/reviving-an-e-commerce-search-engine-using-elasticsearch-)
  * [Video](https://www.youtube.com/watch?v=_h12KHPg_WE)
  * [Video](https://www.youtube.com/watch?v=K-DWcM886Z4)
  * [Video](https://www.youtube.com/watch?v=_h12KHPg_WE)
  * [Video](https://www.youtube.com/watch?v=OoMZPU4EGrU)
  * [Video](https://www.youtube.com/watch?v=FkxAfpvRrbc) -->

  *  [RANGE QUERIES](https://linuxhint.com/elasticsearch-range-query/)
  * [SPELLCHECK FUZZINESS](https://engineering.empathy.co/spellcheck-in-elasticsearch/)
 * [AUTOCOMPLETE](https://opster.com/guides/elasticsearch/how-tos/elasticsearch-auto-complete-guide/)
