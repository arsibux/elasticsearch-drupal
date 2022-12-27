# Elasticsearch Drupal 8

Elasticsearch integration with Drupal 8 CMS using core module SEARCH API and features contrib modules Elasticsearch Connector.

**TasK** --SEARCH PERFORMANCE OPTIMIZATION --
Optimize search related ReSTful APIs using external search engin. Currently the system is using drupal internal database search and providing custom ReST API that fetching data from drupal linked database.
**Challenge**: Integration of all search related drupal exposed ReSTful APIs with elasticsearch service.

### SYSTEM SPECIFICATIONS

- DRUPAL:8.9.13 as BACKEDN CMS Exposing ReSTful APIs.
- DATABASE: Mariadb: 10.4
- ANGULAR: FRONTEND Client.
- SEARCH: Drupal is using Internal DATABASE SEARCH { Custom API for fetching data from database }

We have two solutions to integrate search engin with drupal CMS

- SOLUTION # 1 {Using core and contrib Drupal modules }
- SOLUTION # 2 { Drupal Custom Module Development }

## SOLUTION # 1 {Using core and contrib Drupal modules }

In this method we can use drupal contrib modules to integrate elasticsearch with drupal cms/

**DEPENDENCIES**

- Elastissearch Service.
- Elasticseacrch Connector Drupal contrib module.
- Search API Drupal core module.
- Views core module.
- Webservices drupal core modules.

![anatomy](https://github.com/arsibux/elasticsearch-drupal/blob/main/_draw/anatomy.png)

**ES INTEGRATION WITH D8 CMS**

Elastic Search Setup can be achieved by following two ways.

- Setup Elasticsearch Server @VM

  For connection b/w drupal and elasticsearch, drupal provides a contrib module [**elasticsearch_connector**](https://www.drupal.org/project/elasticsearch_connector) responsible to establish connection.

  Note:This project is not covered by Drupal’s security advisory policy.
  but **{ 5,161 }** sites report using this module

  - [**SECURITY**](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/SECURITY.md)
  - [**LIENCENE**](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/LICENSE.md)

- Cloud based Service

  - [elastic.co](https://www.elastic.co/cloud/)
  - [AWS](https://aws.amazon.com/marketplace/pp/prodview-voru33wi6xs7k)
  [For Connection contrib module](https://www.drupal.org/project/elasticsearch_aws_connector).

  Note:This project is not covered by Drupal’s security advisory policy.
  but **{ 353 }** sites report using this module sites report using this module.

**DRUPAL MODULES INSTALLATION AND CONFIGURATION**

1. Search API enable and elasticearch_connector downlaod via composer and enabled.
   ![modules](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/es_enabled.png)
2. Establish connection between DRUPAL CMS and ELASTICSEARCH by using UI fo elasticsearch_connector.
   ![es](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/es.png)
3. Configur search_api with elasticsearch.
   ![search_api](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/search_api.png)
4. Creating index {idx_product} product in Search API.
   ![idx](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/idx.png)
5. Configur datasource by selecting entity {PRODUCT} and its fields for elasticsearch server.
   ![fields](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/idx.png)
6. Create View {Rest Export Page with path} and select index as content.
   ![views](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/view.png)

**TESTING**

- Web Stack with Elasticsearch Server and Kibana up and running
  ![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/stack.png)
- Total products in drupal CMS DATABASE. **{ 489 }** with both status {published, not}
  ![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/db.png)
- Total products in elasticsearch **{ after and before }** indexing using [**kibana**](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/KIBANA.md).
  - Before ![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/before.png)
  - After ![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/after.png)
- Check API in Postman
  ![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/postman.png)
- Check total number of the products in ReStful API.
  - without keyword
    ![total](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/total.png)
  - with keyword
    ![filtered](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/filtered.png)

<hr>

<!-- ## SOLUTION # 2 { Custom Development }

### NEW MODULE { zain_elasticsearch } -->

### KIBANA

- [Searching APIs in Kibana](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/KIBANA.md)

### EXAMPLES

- [NASA SCIENCE](https://science.nasa.gov/) Drupal + Elasticsearch
- [USGS STORE](https://store.usgs.gov/)

### WORK LOGS

- [ADDED: 19-DEC-2022 - 26-DEC-2022](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/26_DEC_TO_02_JAN.md)
- [ADDED: 26-DEC-2022 - 02-JAN-2023]

### REFERENCES

- [ES Integration with Drupal CMS](https://www.lullabot.com/articles/indexing-content-from-drupal-8-to-elasticsearch)
- [ELASTICSEARCH RANGE QUERIES](https://linuxhint.com/elasticsearch-range-query/)
- [SPELLCHECK FUZZINESS](https://engineering.empathy.co/spellcheck-in-elasticsearch/)
- [ELASTICSEARCH AUTOCOMPLETE](https://opster.com/guides/elasticsearch/how-tos/elasticsearch-auto-complete-guide/)

<!-- -[Video](https://opendistro.github.io/for-elasticsearch-docs/docs/elasticsearch/ux/)
- [Video](https://medium.com/quantyca/reviving-an-e-commerce-search-engine-using-elasticsearch-)
- [Video](https://www.youtube.com/watch?v=_h12KHPg_WE)
- [Video](https://www.youtube.com/watch?v=K-DWcM886Z4)
- [Video](https://www.youtube.com/watch?v=_h12KHPg_WE)
- [Video](https://www.youtube.com/watch?v=OoMZPU4EGrU)
- [Video](https://www.youtube.com/watch?v=FkxAfpvRrbc) -->
