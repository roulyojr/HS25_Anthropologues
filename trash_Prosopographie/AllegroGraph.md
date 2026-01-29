URL : https://ag132vl3gqf5dw9c.allegrograph.cloud/webview/welcome


Requête pour liste des anthropologues : 
```
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/> 
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?person ?label
WHERE {
SERVICE <https://dbpedia.org/sparql> {
    dbr:List_of_anthropologists ?p ?person.
    ?person a dbo:Person;
            dbo:birthDate ?birthDate ;
        rdfs:label ?label.
        BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)
        FILTER ( ?birthYear > 1770  && LANG(?label) = 'en')
    }
}
```

fait la liste des propriétés : 

PREFIX dbo: <http://dbpedia.org/ontology/> 

SELECT ?P # (COUNT(*) as ?number)
WHERE {?s ?P ?O}


Le construct permet de créer les triplets