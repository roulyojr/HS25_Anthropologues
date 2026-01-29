"pour sélectionner objets et propriétés"

SELECT *
WHERE {
  <http://dbpedia.org/resource/Claude_Lévi-Strauss> ?p ?o
}

"pour regrouper par propriété, puis compter les instances"

SELECT ?p(COUNT(*)AS?number)
WHERE {
  <http://dbpedia.org/resource/Claude_Lévi-Strauss> ?p ?o
}
GROUP BY ?p

"pour regrouper par propriété, puis compter les instances"

SELECT ?p(COUNT(*)AS?number)
WHERE {
  <http://dbpedia.org/resource/Claude_Lévi-Strauss> ?p ?o
}
GROUP BY ?p
ORDER BY DESC(?number)

"le prefix du début permet de faire l'économie du lien URI complet ; resource est les URI qui identifient les objets ; "a" remplace "is a"" -> faute de synthaxe

PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT DISTINCT ?o1 
WHERE { 
  dbr:List_of_anthropologists ?o1.
  ?o1 a dbo:Person.
  }
LIMIT 10