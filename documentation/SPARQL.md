* Dans quels contextes nationaux sont nées les premières écoles dédiées à l'anthropologie ?

        Lister les dates de naissance d'anthropologues dans l'ordre croissant et les universités pour lesquelles ils et elles travaillent (je me suis aidé du Web pour le GROUP_CONCAT et le OPTIONAL)

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


Y a-t-il des tendances nationales quand à l'apport d'arguments théoriques en anthropologie ?

        Lister les anthropologues, leur nationalité et leur école de pensée

        