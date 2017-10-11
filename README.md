# 2015-2016_GLA_Projet2
Push/pull sur le profil de WindyWay96 - fork à consulter 
Le projet consiste en 4 phases - 
1. Cahier des charges et analyse

L'analyse est un modèle conceptuel permettant de spécifier les fonctions exigées d'un système ou d'un composant. Il décrit généralement ce dont l'utilisateur a besoin, et les propriétés que doivent avoir les entrées-sorties. Le but est de permettre aux développeurs de savoir ce qu'ils doivent construire, aux testeurs quels jeux de tests produire, et aux clients ce qu'ils vont obtenir.

2. Cahier de conception

L'étape de conception est un modèle physique et va plus loin. Elle décrit plus précisément les technologies employées et la manière dont les approches algorithmiques sont abordées. Elle dresse une architecture pouvant aller jusqu'aux détails algorithmiques (e.g. opérateur loop en UML, types de données...), et agit comme un document nécessaire au maintien du développement logiciel. Entre autres, ce document permet aux futurs développeurs d'aborder un projet en marche, sans toucher l'implémentation.

3. Implémentation
L'implémentation est le code, instanciant directement la conception. Il doit être envoyé sous la forme d'une archive TAR/GZ contenant un court README. Il doit être obligatoirement disponible sur un dépôt privé GitHub, et partagé aux chargés de TP en tant que collaborateur.

4. Soutenance
Vous aurez à votre disposition un projecteur et 15 minutes afin de présenter l'ensemble de votre projet (déroulement, organisation, technicité des approches, et démonstration avec tests pertinents). Vous devrez être capable de répondre aux 10 minutes de questions qui porteront sur l'ensemble de vos rendus. Des cas de tests aux limites seront proposés vos examinateurs.

Contexte
Plusieurs amis veulent sortir à Paris afin de fêter leurs retrouvailles et ont envie de passer une bonne soirée. Pour cela, ils auraient besoin d'organiser successivement trois sorties
	1	Boire un verre dans un bar sympa
	2	Manger au restaurant (attention: un des amis n'aime pas les kebabs!)
	3	Sortir en boîte de nuit
Exigences
Votre projet consiste à fournir une interface avec en:
	•	Entrée: une date, une liste de personnes ayant des contraintes d'adresses (là où ils habitent) et de préférences alimentaires
	•	Résultat: une liste chronologique de trois adresses (bar, resto, boîte)
Parmi les propriétés que l'on demande sur votre système, vous devrez considérer qu'une sortie prend un certain temps (que vous déterminerez arbitrairement), que le déplacement d'un point à un autre prend aussi un certain temps (qui devra être calculé), et que les sorties ont des horaires d'ouverture coïncidant avec les critères précédents.
Pour aller plus loin, vous êtes libres de prendre des initiatives afin d'enrichir votre projet: permettre à l'utilisateur de refuser un triplet de sorties et générer d'autres, considérer des trajets à vélo et donner les positions de Vélib les plus proches du domicile, se déplacer en voiture et désigner le Sam de la soirée... Notez cependant que toute fonctionnalité doit être documentée et que son absence lors de l'implémentation (e.g. manque de temps, impossibilité de l'API à fournir des informations spécifiques...) entraîne des pénalités. Les étapes d'analyse, de conception et d'implémentation sont donc liées et aucune ne devrait être négligée.
Programmation
Le choix du langage de programmation est laissé libre mais vous devez obligatoirement utiliser des APIs en ligne. Celles-ci sont accessibles par des requêtes HTTP et par réponses en JSON, que vous devrez parser afin de les manipuler. Vous devez vous inscrire sur Google API Console afin d'obtenir une clé d'authentification d'accès aux APIs :
	1	vous devez créer un projet;
	2	activer les services Google Maps Distance Matrix API et Google Places API Web Service (rubrique Bibliothèque/Library);
	3	générer une clé API (rubrique Identifiants/Credentials).

A titre d'exemple, nous pouvons demander une liste de restaurants dans un rayon de 500 mètres autour de la Place de la Bastille ayant pour thème les burgers, avec une simple requête HTTP avec l'API Google Places en tapant: https://maps.googleapis.com/maps/api/place/nearbysearch/json?location=48.855218,2.368622&radius=500&type=restaurant&name=burger&key=<VOTRE CLE API>
Pour manipuler les données récupérées, vous pouvez utiliser différents langages de programmations supportant le parsing JSON. L'archive suivante contient un bout de programme en Java permettant de manipuler la requête précédente
		NearbySearchExample.zip

Enfin, vous pouvez aussi demander à calculer le temps de trajet entre deux points avec l'API Google Maps avec la requête: https://maps.googleapis.com/maps/api/distancematrix/json?origins=Paris,FR&destinations=Orsay,FR&key=<VOTRE CLE API>
