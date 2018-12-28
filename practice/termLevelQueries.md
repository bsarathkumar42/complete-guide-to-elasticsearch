#Please write a query matching products that didn’t sell very well, being products where the “sold” field has a value of less than 10 (sold < 10).

POST /product/default/_search?search_type=query_then_fetch&scroll=100m&size=50
{
  "query": {
    "range": {
      "sold": {
        "lt": 10
      }
    }
  }
}


#Please write a query that matches products that sold okay, meaning less than 30 and greater than or equal to 10 (sold < 30 && sold >= 10).

POST /product/default/_search?search_type=query_then_fetch&scroll=100m&size=50
{
  "query": {
    "range": {
      "sold": {
        "lt": 30,
        "gte": 10
      }
    }
  }
}



#Please write a query that matches documents containing the term “Meat” within the “tags” field.

POST /product/default/_search?search_type=query_then_fetch&scroll=100m&size=50
{
  "query": {
    "match": {
      "tags.keyword": "Meat"
    }
  }
}

#Please write a query matching documents containing one of the terms "Tomato" and "Paste" within the "name" field.



#Hint: The query might not match anything... ;-)
#
#Please write a query that matches products with a "name" field including “pasta”, “paste”, or similar. The query should be dynamic and not use the "terms" #query clause.
#
#Please write a query that matches products that contain a number within their "name" field.