Faire figurer les noms des organisations aux côtés des noms des personnes (avec dates de fréquentation) : 

SELECT o.name, p.name, f.date_begin, f. date_end 
FROM frequentation f
	JOIN person p on f.fk_person = p.pk_person
	JOIN organisation o on f.fk_organisation = o.pk_organisation;

Faire figurer les noms des personnes, leur type et lieu de formation :

CREATE VIEW NewView_1 AS SELECT p.name, f."type", gp.name 
FROM formation f
JOIN person p on f.fk_person = p.pk_person
JOIN geographical_place gp on f.fk_geographical_place = gp.pk_geographical_place;

Faire figurer les noms des villes à côté de leur typologie : 

SELECT gp.name, gpt.name, gpt.definition
FROM geographical_place gp 
JOIN geographical_place_type gpt on gp.fk_geo_place_type = gpt.pk_geographical_place_type ;