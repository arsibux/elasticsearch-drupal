- Setting for search as you type

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

- Search

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

- Spellcheck Fuzziness

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

- Range

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

- Semantic
- Fulltext
