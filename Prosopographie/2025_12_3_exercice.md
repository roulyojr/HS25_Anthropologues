PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT ?person ?object
WHERE { 
dbr:List_of_anthropologists ?p ?person.
?person a dbo:Person;
        dbo:birthDate ?birthDate ;
    <http://www.w3.org/2002/07/owl#sameAs> ?object.
    BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)
    FILTER ( ?birthYear > 1770)
}
LIMIT 100

"le same as permet de rechercher des objets de la classe personne dans les autres bases de données auxquelles dbpedia est connectée"

PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
SELECT ?addr (COUNT(*) AS ?number)
WHERE { 
dbr:List_of_anthropologists ?p ?person.
?person a dbo:Person;
        dbo:birthDate ?birthDate ;
    owl:sameAs ?object.
    BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)
    FILTER ( ?birthYear > 1770)
BIND(SUBSTR(STR(?object), 1, 20) as ?addr)
}
GROUP BY ?addr
ORDER BY DESC(?number)

"le bind l. 27 fait une opération sur une variable, dont on met de résultat dans une nouvelle table "?addr""

Pour sélectionner uniquement le meilleur résultat de la recherche, on applique un filtre : 
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX owl: <http://www.w3.org/2002/07/owl#>

SELECT ?person ?object
WHERE { 
dbr:List_of_anthropologists ?p ?person.
?person a dbo:Person;
        dbo:birthDate ?birthDate ;
    owl:sameAs ?object.
    BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)
    FILTER (CONTAINS(STR(?object), 'gnd'))
}
LIMIT 10

"cela permet de partager l'information facilement, reste à voir si l'information est intéressante ou pas"

PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT ?person ?gndUri ?p1 ?o1
WHERE {

SERVICE <https://dbpedia.org/sparql> {
SELECT ?person ?gndUri ?object
    WHERE { 
    dbr:List_of_anthropologists ?p ?person.
    ?person a dbo:Person;
            dbo:birthDate ?birthDate ;
        owl:sameAs ?object.
        BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)
        FILTER ( ?birthYear > 1770 && CONTAINS(STR(?object), 'gnd'))
        BIND( URI(REPLACE(STR(?object), 'http', 'https'))  AS ?gndUri)
    }
    LIMIT 3
}

?gndUri ?p1 ?o1
}

"fait la requête dans dbpedia, 