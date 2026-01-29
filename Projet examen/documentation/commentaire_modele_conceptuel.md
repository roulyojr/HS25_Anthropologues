Ce document contient le commentaire, avec exemples, du modèle conceptuel

## Formation
Une formation universitaire ou autre parcours équivalent
Il s'agit d'une classe objet (persistent item)

### Propriétés
Date de début et de fin de la formation, type (philosophie, philologie, ethnographie, etc)

### Relations
Localisation du lieu de formation
Une formation peut être l'objet d'une participation
(Génère une idée théorique)


## Arrière-plan socio-économique
Informations sur la généalogie financière et social de l'individu
Il s'agit d'une classe objet (persistent item)

### Propriétés
Si disponible, statut socio-économique familial (métiers exercés, ou type de métiers : ouvriers, profession libérale, industriels...) et religion (catholicisme, judaïsme)


## Person
Tout être humain.
Il s'agit d'une classe objet (persistent item)

### Propriétés
Nom standard, date de naissance et de décès, courant de pensée (influences principales et générales : structuralisme, fonctionnalisme ou autre) et nationalité.


## Fréquentation
Fréquenter un organisme pendant une période donnée (entretien des contacts réguliers ou ponctuels avec une organisation, dont le rôle qui y est joué peut différer (professeur ordinaire, invité, étudiant))

Il s'agit d'une classe temporalité (temporal entity)

### Propriétés
Date de début, de fin et rôle endossé dans la fréquentation de l'organisation.

### Relations
Une relation de fréquentation peut comprendre une et une seule personne, une et une seule production et on peut associer une (et une seule) organisation auprès de laquelle l'activité est exercée.


## Organisation
Tout groupe d'êtres humains constitué de plus de deux personnes, entretenant des rapports réguliers
Il s'agit d'une classe objet (persistent item)

### Propriétés
Nom, définition (organisation privée, universitaire, association), année de fondation (de l'institution)

### Relations
L'organisation est située à un emplacement géographique. On considérera le siège effectif de l'organisation.


## Production
Écrit scientifique, conférence audio/audiovisuelle, émission, essai littéraire
Il s'agit d'une classe objet (persistent item)

### Propriétés
Titre, année(s) de parution, revue, maison d'édition, langue originale

### Relations
Mobilise une idée générée lors du parcours académique 


## Emplacement géographique
Lieu géographique
Il s'agit d'une classe objet (persistent item)

### Propriétés
Nom du lieu, État où il est situé

### Relations
A comme type (caractérisation du lieu en fonction de critères topographiques, sociaux, technologiques ou historiques)


## Geographical place type
Type d'endroit représenté par l'emplacement géographique
Il s'agit d'une classe objet (persistent item)

### Propriétés
Nom, définition (ville, capitale, village, région)

### Relations
Une relation réflexive de spécialisation, termes plus génériques associés à des termes plus précis.
Par exemple 'métropole' spécialise le terme de 'ville'.


## Tag
Un mot clé qui introduit un classement de recherche, généralement lié au questionnement.

### Relations
Relation réflexive (d'un classe vers elle même) qui créer une hiérarchie de mots clés.


## Idée
Élaboration originale de la pensée, permettant, en particulier, de répondre à une situation, d'être à l'origine d'une action, d'une œuvre ou d'une invention originale

### Propriétés
Définition (succincte de la thèse), Arrière-plan théorique (de quel courant anthropologique est tirée la thèse, p.ex. diffusionisme, évolutionnisme, fonctionnalisme)


## Production-Idea Association
Fréquenter un organisme pendant une période donnée (entretien des contacts réguliers ou ponctuels avec une organisation, dont le rôle qui y est joué peut différer (professeur ordinaire, invité, étudiant))

Il s'agit d'une classe d'association n à n

### Propriétés
Associe les productions aux idées théoriques

### Relations
Une relation de Production-Idée permet d'associer plusieurs productions à une idée et inversément. Dans ce cas, on créera plusiseurs entrées pour associer chaque production au nombre d'idées qu'il mobilise.
