* Dans quels contextes nationaux sont nées les premières écoles dédiées à l'anthropologie ?

        Lister les dates de naissance d'anthropologues dans l'ordre croissant et les universités pour lesquelles ils et elles travaillent (je me suis aidé du Web pour le GROUP_CONCAT et le FILTER)

                    SELECT ?person 
                (STR(?label) AS ?persName) 
                ?birthYear
                (GROUP_CONCAT(DISTINCT STR(?institutionLabel); separator=", ") AS ?institutions)
            WHERE { 
                dbr:List_of_anthropologists ?p ?person.

                ?person a dbo:Person ;
                        dbo:birthDate ?birthDate ;
                        rdfs:label ?label .

                BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)

                OPTIONAL {
                    ?person dbo:institution ?institution .
                    ?institution rdfs:label ?institutionLabel .
                }
            }
            GROUP BY ?person ?label ?birthYear
            ORDER BY ?birthYear


            -> faiblesse : infobox ne contient pas forcément l'information de l'institution, surtout chez les chercheurs.euses moins connus

            Correction : étonnement, remplacer 'institution' par 'workplace' donne plus de résultats

                SELECT ?person 
                (STR(?label) AS ?persName) 
                ?birthYear
                (GROUP_CONCAT(DISTINCT STR(?workplacesLabel); separator=", ") AS ?workplaces)
            WHERE { 
                dbr:List_of_anthropologists ?p ?person.

                ?person a dbo:Person ;
                        dbo:birthDate ?birthDate ;
                        rdfs:label ?label .

                BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)

                OPTIONAL {
                    ?person dbp:workplaces ?workplaces .
                    ?workplaces rdfs:label ?workplacesLabel .
                }
            }
            GROUP BY ?person ?label ?birthYear
            ORDER BY ?birthYear


            Requête syntaxiquement la même, mais en cherchant l'almaMater (axé formation), qui est souvent présent dans l'infobox : 

                            SELECT ?person 
                (STR(?label) AS ?persName) 
                ?birthYear
                (GROUP_CONCAT(DISTINCT STR(?almaMaterLabel); separator=", ") AS ?almaMater)
            WHERE { 
                dbr:List_of_anthropologists ?p ?person.

                ?person a dbo:Person ;
                        dbo:birthDate ?birthDate ;
                        rdfs:label ?label .

                BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)

                OPTIONAL {
                    ?person dbo:almaMater ?almaMater .
                    ?almaMater rdfs:label ?almaMaterLabel .
                }
            }
            GROUP BY ?person ?label ?birthYear
            ORDER BY ?birthYear

Y a-t-il des tendances nationales quand à l'apport d'arguments théoriques en anthropologie ?

        Lister les anthropologues, leur nationalité et leur école de pensée

                PREFIX dbo: <http://dbpedia.org/ontology/>
                PREFIX dbp: <http://dbpedia.org/property/>
                PREFIX foaf: <http://xmlns.com/foaf/0.1/>
                PREFIX dbr: <http://dbpedia.org/resource/>

                SELECT ?name ?nationality ?school
                WHERE {
                ?anthropologist dbo:occupation dbr:List_of_Anthropologists ;
                                foaf:name ?name ;
                                dbo:nationality ?nationality ;
                                dbo:school ?school .
                }

                            théoriquement correcte mais ne fonctionne pas dans l'éditeur SPARQL
