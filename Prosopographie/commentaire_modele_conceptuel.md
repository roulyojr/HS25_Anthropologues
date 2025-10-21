Ce document contient le commentaire, avec exemples, du modèle conceptuel

## Birth
Naissance de la personne
Il s'agit d'une classe objet (persistent item)

### Propriétés
Date de naissance

### Relations
Localisation de la naissance
Donne vie à une personne

## Person

Tout être humain. 

### Propriétés

Nom standard (aucun surnom n'est généralement donné dans la littérature scientifique), type de formation (philosophie, anthropologie, ethnographie, histoire, géographie ou autres), courant de pensée (influences principales et générales : structuralisme, fonctionnalisme ou autre) et langue.
Il s'agit d'une classe objet (persistent item)

### Relations

Produit (création d'une oeuvre ou d'un écrit scientifique)

Fréquente (entretien des contacts réguliers ou ponctuels avec une organisation)

Obtient un poste d'enseignement (est titulaire d'une chaire ou d'un département qui lui permet de développer ses recherches)

Suit des cours à (sous la direction de tel professeur)

## Organisation

Toute groupe d'êtres humains constitué de plus de deux personnes, entretenant des rapports réguliers
Il s'agit d'une classe objet (persistent item)

### Propriétés

Nom, type (organisation privée, universitaire, association), siège (lieu du siège), fondation (de l'institution)

### Relations

Influence (transfert de domaine de recherche ou d'idée entre deux institutions ou plus)

Subventionne la recherche (soutien actif d'une organisation à la création d'un travail scientifique d'un sujet x)

Est situé à : endroit géographique

Une relation réfléxive de spécialisation, termes plus génériques associés à des termes plus précis.
Par exemple 'recherche en psychologie comportementale' spécialise le terme de 'université'.

## Oeuvre

Écrit scientifique, conférence audio/audiovisuelle, émission
Il s'agit d'une classe objet (persistent item)

### Propriétés

Référence de la publication, année(s) de parution, langue d'origine et traductions éventuelles, lieu de production

### Relations

Influence (modifie ou créer un intérêt chez une personne qui produira un travail scientifique s'aidant des méthodes, idées ou arguments avancés par l'ouvrage scientifique)

## Geographical place

Lieu géographique
Il s'agit d'une classe objet (persistent item)

### Propriétés

Nom du lieu, nation où il est situé, coordonnées géographiques

### Relations

A comme type (caractérisation du lieu en fonction de critères topographiques, sociaux, technologiques ou historiques)

## Geographical place type

Type d'endroit représenté par la place géographique
Il s'agit d'une classe objet (persistent item)

### Propriétés

Nom, définition (ville, capitale, village, région)

### Relations

Une relation réfléxive de spécialisation, termes plus génériques associés à des termes plus précis.
Par exemple 'métropole' spécialise le terme de 'ville'.

## Pursuit (pas intégré dans le modèle pour l'instant)

Le fait d'avoir telle occupation ou activité durant telle période 
Il s'agit d'une classe temporalité (temporal entity)

Exemple: "Kepler was a mathematics teacher at a seminary school in Graz" (Wikipedia)

### Relations

Une _Pursuit_ peut comprend une et une seule personne, une et une seule occupation (ces deux relations sont nécessaires) et éventuellement on peut associer une (et une seule) organisation auprès de laquelle l'activité est exercée.

Si plusieurs organisation sont concernées par une activité, plusieurs individus de la classe _Pursuit_ seront créées.

