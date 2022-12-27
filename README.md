# Elasticsearch Drupal 8

Elasticsearch integration with Drupal 8 CMS using core module SEARCH API and features contrib modules Elasticsearch Connector.

**TASK** Optimize search related ReSTful APIs using external Search Engine. Currently the system is using drupal internal database search and providing custom ReST API that fetching data from drupal linked database.

**SYSTEM SPECIFICATIONS**

- [DRUPAL: 8.9.13](https://www.drupal.org/project/drupal/releases/8.9.13) CMS as BACKEND
  - [Commerce: 8.x-2.15](https://www.drupal.org/project/commerce/releases/8.x-2.15)
  - Webservices
- DATABASE: Mariadb: 10.4
- ANGULAR: FRONTEND Client.

We have two solutions to integrate Elasticsearch Server with Drupal CMS

- SOLUTION # 1 { Core and Contrib Drupal Modules }
- SOLUTION # 2 { Drupal Custom Module Development }

## SOLUTION # 1 { Using Core and Contrib Drupal Modules }

Drupal contrib modules to integrate Elasticsearch with Drupal CMS.

**DEPENDENCIES**

- [Elastissearch Service](https://www.elastic.co/)

  - [Free and Open](https://www.elastic.co/about/free-and-open)

- [Elasticseacrch Connector](https://www.drupal.org/project/elasticsearch_connector) Drupal Contrib Module.
- [Search API](https://www.drupal.org/project/drupal/releases/8.9.13) Drupal Core Module.
- [Views](https://www.drupal.org/project/drupal/releases/8.9.13) Core Module.
- [Webservices](https://www.drupal.org/project/drupal/releases/8.9.13) Drupal Core Modules.

![anatomy](https://github.com/arsibux/elasticsearch-drupal/blob/main/_draw/anatomy.png)

**ES INTEGRATION WITH D8 CMS**

Elasticsearch Setup can be achieved by following two ways.

- Setup Elasticsearch Server @VM
- Cloud based services
  - [elastic.co](https://www.elastic.co/cloud/)
  - [AWS](https://aws.amazon.com/marketplace/pp/prodview-voru33wi6xs7k)

For connection b/w Drupal and Elasticsearch, Drupal provides a contrib module [**Elasticsearch Connector**](https://www.drupal.org/project/elasticsearch_connector) responsible to establish connection.

Note:This project is not covered by Drupal’s security advisory policy.
but **{ 5,161 }** sites report using this module

- Last **RELEASE**

- [**SECURITY**](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/SECURITY.md)

- **LICENSE** GNU GENERAL PUBLIC LICENSE Version 2, June 1991


**DRUPAL MODULES INSTALLATION AND CONFIGURATION**

1. Search API and Elasticearch Connector enabled.

![modules](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/es_enabled.png)

2. Establish connection between DRUPAL CMS and ELASTICSEARCH by using UI fo Elasticearch Connector.

![es](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/es.png)

3. Configur Search API and Elasticearch Connector.

![search_api](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/search_api.png)

4. Creating index {idx_product} product in Search API.

![idx](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/idx.png)

5. Configur datasource by selecting entity {PRODUCT} and its fields for elasticsearch server.

![fields](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/idx.png)

6. Create View {Rest Export Page with path} and select index as content.

![views](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/steps/view.png)

**TESTING**

1. Web Stack with Elasticsearch Server and Kibana up and running

![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/stack.png)

2. Total products in drupal CMS DATABASE. **{ 489 }** with both status {published, not}

![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/db.png)

3. Total products in elasticsearch **{ after and before }** indexing using [**kibana**](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/KIBANA.md).

- Before

![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/before.png)

- After

![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/after.png)

4. Check API in Postman

![stack](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/postman.png)

5. Check total number of the products in ReStful API.

- without keyword

![total](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/total.png)

- with keyword

![filtered](https://github.com/arsibux/elasticsearch-drupal/blob/main/images/testing/filtered.png)

<hr>

## SOLUTION # 2 { Drupal Custom Module Development }

<!-- ### NEW MODULE { zain_elasticsearch } -->

### KIBANA

- [Searching APIs in Kibana](https://github.com/arsibux/elasticsearch-drupal/blob/main/_progress/KIBANA.md)

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
