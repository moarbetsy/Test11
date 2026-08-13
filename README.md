Groupe Ferguson — Plan devis technique final

Site : GroupeFerguson.ca
Projet : Système d’estimation, Auto-Quote, soumission, réservation et paiement pour le marquage de stationnements commerciaux
Version : Plan final

⸻

1. Objectif du système

Créer un parcours Web simple permettant à un client de passer de la demande initiale à un projet réservé et payé, tout en offrant deux modes de traitement :

1. Soumission Groupe Ferguson — l’équipe prépare la soumission et contacte le client dans les 24 heures.
2. Auto-Quote — le client utilise la carte satellite, obtient instantanément une quote, peut la réserver et effectuer son paiement.

Principe central

Le client fournit les informations de base. Groupe Ferguson s’occupe de la soumission, ou le client peut choisir l’Auto-Quote pour obtenir son prix immédiatement.

⸻

2. Parcours client

ACCUEIL
   ↓
1. CLIENT
   ↓
2. ADRESSE DU PROJET
   ↓
3. NOMBRE DE PLACES
   ↓
4. SYMBOLES
   ↓
5. TYPE DE STATIONNEMENT
   ↓
6. TYPE DE TRAVAUX
   ↓
7. CHOIX DU PARCOURS
      ├───────────────┐
      ↓               ↓
SOUMISSION 24 H    AUTO-QUOTE
                      ↓
                CARTE SATELLITE
                      ↓
                ZONE DE TRAVAUX
                      ↓
                SUPERFICIE
                      ↓
                CALCUL DU PRIX
                      ↓
                    QUOTE
                      ↓
                  ACCEPTATION
                      ↓
                  RENDEZ-VOUS
                      ↓
                    PAIEMENT
                      ↓
                  CONFIRMATION

⸻

3. Accueil

Proposition principale

Marquage et traçage de stationnements commerciaux

Présenter brièvement Groupe Ferguson et ses services.

Bouton principal

Obtenir une soumission

Option Auto-Quote

Obtenir une quote instantanément

L’objectif est de présenter immédiatement les deux possibilités sans surcharger la page.

⸻

4. Étape 1 — Client

Le client indique s’il agit comme :

○ Entreprise
○ Particulier

Informations

* Nom
* Nom de l’entreprise, si applicable
* Téléphone
* Courriel

Ces informations constituent le dossier client.

⸻

5. Étape 2 — Adresse du projet

Question

Quelle est l’adresse du stationnement à marquer?

Le client entre l’adresse.

Le système :

* valide l’adresse;
* la normalise;
* récupère latitude et longitude;
* crée le projet;
* calcule la distance depuis Groupe Ferguson.

⸻

6. Calcul automatique de la distance

Le système calcule la distance entre :

Point de référence Groupe Ferguson

et

Adresse du projet

Donnée enregistrée

distance_km

Lorsque le calcul sert à déterminer des frais de déplacement, utiliser de préférence la distance routière.

Exemple

Adresse du projet
       ↓
Calcul routier
       ↓
32,6 km
       ↓
Zone tarifaire
       ↓
Frais de déplacement éventuels

Les règles de distance doivent être configurables dans l’administration.

Exemple de configuration

0–25 km       → Zone 1
25–50 km      → Zone 2
50–75 km      → Zone 3
75 km +       → Sur demande

Les valeurs ci-dessus sont des exemples et ne constituent pas les tarifs définitifs.

⸻

7. Étape 3 — Nombre de places

Après l’adresse :

Combien de places de stationnement?

[ __________ ]

Le nombre de places est enregistré dans le projet et transmis automatiquement à la soumission ou à l’Auto-Quote.

⸻

8. Étape 4 — Symboles

Question

Quels symboles devez-vous faire marquer?

Le client sélectionne les types et quantités.

Symbole	Quantité
PMR	[ ]
Flèches	[ ]
Réservé	[ ]
Recharge électrique	[ ]
Autre	[ ]

Bouton :

+ Ajouter un symbole

Option :

Aucun symbole

⸻

9. Étape 5 — Type de stationnement

○ Stationnement extérieur
○ Stationnement sous-terrain
○ Extérieur + sous-terrain

Si sous-terrain

Afficher un champ supplémentaire :

Commentaires / particularités

Permettre notamment d’indiquer :

* accès particulier;
* hauteur limitée;
* contraintes;
* circulation;
* heures d’accès;
* autres informations pertinentes.

Des photos peuvent être demandées lorsque nécessaire.

⸻

10. Étape 6 — Type de travaux

○ Nouveau marquage
○ Repeinture
○ Nouveau marquage + repeinture

⸻

11. Choix du parcours

Une fois les informations de base recueillies, présenter deux options.

Option A — Soumission Groupe Ferguson

Recevoir ma soumission

Texte :

Nous préparerons votre soumission et communiquerons avec vous dans les 24 heures.

Le client n’a pas besoin d’utiliser la carte.

Le dossier est transmis à Groupe Ferguson avec toutes les informations déjà recueillies.

⸻

Option B — Auto-Quote

Obtenir mon Auto-Quote maintenant

Texte :

Dessinez votre zone de travaux sur la carte et obtenez votre quote instantanément.

C’est uniquement à ce moment que le client accède à la carte satellite.

⸻

12. Parcours Soumission 24 heures

Si le client choisit Recevoir ma soumission :

Informations client
        ↓
Adresse
        ↓
Places
        ↓
Symboles
        ↓
Stationnement
        ↓
Travaux
        ↓
Distance
        ↓
Dossier Groupe Ferguson
        ↓
Préparation de la soumission
        ↓
Envoi au client

Le client reçoit une notification confirmant que sa demande a été reçue.

Message

Votre demande a été reçue. Groupe Ferguson préparera votre soumission et communiquera avec vous dans les 24 heures.

Le délai de 24 heures doit être présenté conformément aux heures de service et aux conditions commerciales réelles de Groupe Ferguson.

⸻

13. Parcours Auto-Quote

Si le client choisit Auto-Quote, afficher la carte satellite.

L’adresse précédemment fournie est automatiquement utilisée.

Le client n’a pas besoin de rechercher à nouveau son stationnement.

⸻

14. Carte satellite

Instruction

Tracez approximativement la zone à travailler.

Le client dessine le périmètre de la zone.

Le système calcule :

* superficie;
* périmètre;
* coordonnées;
* zone de travaux.

Principe UX

Le client n’a pas besoin de mesurer.

La zone peut être approximative.

Le moteur de calcul doit tenir compte de cette incertitude.

⸻

15. Auto-Quote

Le moteur utilise les informations recueillies avant la carte et les données géographiques.

Client
+
Adresse
+
Distance
+
Nombre de places
+
Symboles
+
Type de stationnement
+
Type de travaux
+
Zone dessinée
+
Superficie
+
Règles tarifaires
=
AUTO-QUOTE

⸻

16. Moteur de prix

Les paramètres doivent être configurables par Groupe Ferguson.

Paramètres possibles

* tarif au m²;
* tarif par place;
* prix par symbole;
* type de travaux;
* supplément sous-terrain;
* frais de déplacement;
* zone kilométrique;
* prix minimum;
* frais supplémentaires;
* taxes;
* rabais.

Aucun tarif commercial ne doit être codé directement dans l’interface.

⸻

17. Présentation du prix

L’Auto-Quote doit clairement indiquer qu’il s’agit d’une quote générée automatiquement.

Exemple :

Auto-Quote

3 850 $

Calculée selon les informations et la zone sélectionnée.

Lorsque l’incertitude est trop importante, le système peut afficher une fourchette :

3 600 $ – 4 100 $

Avis

Cette Auto-Quote est basée sur les informations fournies et la zone approximativement sélectionnée. Le prix peut être ajusté si les conditions réelles du projet diffèrent des informations fournies.

⸻

18. Acceptation de l’Auto-Quote

Si le client accepte :

ACCEPTER L’AUTO-QUOTE

Le système enregistre :

* numéro du projet;
* version de la quote;
* montant;
* données utilisées;
* date;
* heure;
* client.

Le statut devient :

Auto-Quote acceptée

⸻

19. Réservation

Après l’acceptation :

CHOISIR MON RENDEZ-VOUS

Le calendrier affiche uniquement les disponibilités configurées par Groupe Ferguson.

Le client sélectionne :

* date;
* plage horaire.

Le système associe automatiquement :

Client
+
Projet
+
Quote
+
Rendez-vous

Le système doit empêcher les doubles réservations.

⸻

20. Préparation du site

Avant la confirmation du rendez-vous, afficher clairement :

Veuillez vous assurer qu’aucun véhicule ne se trouve dans la zone des travaux au moment de notre arrivée.

Confirmation obligatoire

☐ Aucun véhicule sera présent dans la zone de travaux.
☐ La zone sera libre d'obstacles.
☐ L'accès au stationnement sera disponible.
☐ Les restrictions particulières ont été communiquées.

⸻

21. Paiement

Après l’acceptation et la réservation :

Option 1 — Dépôt

5 % de rabais

Le client paie le dépôt applicable.

Option 2 — Paiement complet

10 % de rabais

Le client règle la totalité du montant.

Important

Les deux rabais ne sont pas cumulables.

Le système doit afficher avant le paiement :

Prix original
Rabais
Montant à payer
Solde éventuel

⸻

22. Paiement Stripe

Stripe traite le paiement.

Le système conserve :

* identifiant de transaction;
* projet;
* montant;
* rabais;
* statut;
* date;
* montant payé;
* solde.

La confirmation du paiement doit être effectuée côté serveur.

Les données sensibles de carte ne doivent pas être stockées directement dans la base de données Groupe Ferguson.

⸻

23. Confirmation

Après paiement :

Projet confirmé

Afficher :

* numéro de projet;
* client;
* adresse;
* travaux;
* nombre de places;
* symboles;
* date;
* heure;
* montant;
* montant payé;
* solde éventuel.

Une confirmation est envoyée au client.

⸻

24. Rappels automatiques

Prévoir :

Confirmation immédiate

Après réservation.

Rappel avant travaux

Inclure :

* aucun véhicule dans la zone;
* zone dégagée;
* accès disponible;
* obstacles retirés;
* restrictions communiquées.

⸻

25. Administration Groupe Ferguson

Tableau de bord

Nouvelles demandes
Demandes à traiter
Soumissions à préparer
Soumissions envoyées
Auto-Quotes
Soumissions acceptées
Rendez-vous
Paiements
Projets à venir
Projets terminés

⸻

26. Fiche projet

Une seule fiche regroupe toutes les informations.

PROJET #GF-XXXXX
CLIENT
- Type : entreprise / particulier
- Nom
- Entreprise
- Téléphone
- Courriel
PROJET
- Adresse
- Latitude
- Longitude
- Distance en km
- Type de stationnement
- Type de travaux
- Nombre de places
TRAVAUX
- Symboles
- Quantités
- Zone
- Superficie
- Commentaires
- Photos
VENTE
- Estimation
- Auto-Quote
- Soumission
- Acceptation
PLANIFICATION
- Rendez-vous
- Statut
PAIEMENT
- Dépôt / complet
- Rabais
- Montant payé
- Solde
HISTORIQUE
- Actions
- Dates
- Versions

⸻

27. Statuts du projet

NOUVELLE DEMANDE
        ↓
À TRAITER
        ↓
SOUMISSION EN PRÉPARATION
        ↓
SOUMISSION ENVOYÉE
        ↓
ACCEPTÉE
        ↓
RENDEZ-VOUS RÉSERVÉ
        ↓
DÉPÔT / PAYÉ
        ↓
PLANIFIÉ
        ↓
TRAVAUX
        ↓
TERMINÉ

Pour l’Auto-Quote :

AUTO-QUOTE
    ↓
ACCEPTÉE
    ↓
RENDEZ-VOUS
    ↓
PAIEMENT

⸻

28. Gestion du calendrier

L’administration permet de définir :

* jours ouvrables;
* heures disponibles;
* durée estimée des travaux;
* temps tampon;
* journées bloquées;
* vacances;
* capacité quotidienne;
* disponibilités exceptionnelles.

⸻

29. Notifications

Client

* demande reçue;
* soumission disponible;
* Auto-Quote générée;
* Auto-Quote acceptée;
* rendez-vous confirmé;
* rappel;
* paiement confirmé;
* projet confirmé.

Groupe Ferguson

* nouvelle demande;
* nouvelle demande à traiter;
* Auto-Quote acceptée;
* soumission acceptée;
* nouveau rendez-vous;
* paiement;
* annulation;
* modification.

⸻

30. Calcul de distance

Le système doit conserver le calcul utilisé pour chaque projet.

Point Groupe Ferguson
        ↓
Adresse du projet
        ↓
Service cartographique
        ↓
Distance routière
        ↓
Distance en km
        ↓
Règle tarifaire
        ↓
Frais de déplacement éventuels

Données à conserver :

distance_km
source_du_calcul
date_du_calcul
zone_tarifaire
frais_appliqués

Cela permet de reproduire le calcul associé à une quote ou une soumission.

⸻

31. Données principales

Client

id
type_client
nom
entreprise
courriel
téléphone

Projet

id
client_id
adresse
latitude
longitude
distance_km
zone_tarifaire
type_stationnement
type_travaux
nombre_places
commentaires

Zone

project_id
polygone
superficie
perimetre
source

Symboles

project_id
type
quantite

Auto-Quote

project_id
prix_base
prix_zone
prix_places
prix_symboles
frais_distance
frais_options
total
version
date

Soumission

project_id
numero
version
montant
taxes
rabais
statut
date

Rendez-vous

project_id
date
heure
statut

Paiement

project_id
stripe_payment_id
type_paiement
montant_original
rabais
montant_paye
solde
statut
date

⸻

32. Sécurité

Prévoir :

* HTTPS;
* authentification sécurisée;
* contrôle des accès;
* protection anti-spam;
* validation serveur;
* validation des fichiers;
* sauvegardes;
* journalisation;
* protection des renseignements personnels;
* validation serveur des paiements Stripe.

⸻

33. Expérience mobile

Le système doit être mobile-first.

Priorités :

1. peu de champs;
2. grandes zones tactiles;
3. progression claire;
4. aucune répétition;
5. carte simple;
6. chargement rapide;
7. une action principale par écran.

⸻

34. Principe de réduction de friction

Le client ne doit jamais :

* mesurer lui-même son stationnement;
* calculer les kilomètres;
* rechercher deux fois son adresse;
* ressaisir le nombre de places;
* ressaisir les symboles;
* appeler pour connaître les disponibilités lorsqu’il utilise l’Auto-Quote.

Principe

Une information saisie une fois est réutilisée partout.

⸻

35. Architecture fonctionnelle

                     GROUPEFERGUSON.CA
                             │
                             ▼
                          CLIENT
                             │
                             ▼
                    INFORMATIONS DE BASE
                             │
                             ▼
                         ADRESSE
                             │
                             ▼
                    CALCUL DE DISTANCE
                             │
                             ▼
                    PLACES + SYMBOLES
                             │
                             ▼
                  TYPE + TRAVAUX
                             │
                             ▼
                  ┌──────────┴──────────┐
                  │                     │
                  ▼                     ▼
             SOUMISSION             AUTO-QUOTE
                24 H                    │
                  │                     ▼
                  │                SATELLITE
                  │                     │
                  │                     ▼
                  │                  ZONE
                  │                     │
                  │                     ▼
                  │                SUPERFICIE
                  │                     │
                  │                     ▼
                  │                CALCUL PRIX
                  │                     │
                  │                     ▼
                  │                   QUOTE
                  │                     │
                  └──────────┬──────────┘
                             ▼
                         ACCEPTATION
                             │
                             ▼
                         CALENDRIER
                             │
                             ▼
                           STRIPE
                             │
                             ▼
                        CONFIRMATION

⸻

36. Différenciation commerciale

Le système repose sur deux propositions simples.

Pour le client qui veut un accompagnement

Envoyez-nous vos informations. Nous préparons votre soumission dans les 24 heures.

Pour le client qui veut aller rapidement

Dessinez votre stationnement et obtenez votre Auto-Quote instantanément.

Cela permet à Groupe Ferguson de servir à la fois les clients qui veulent une interaction humaine et ceux qui privilégient l’immédiateté.

⸻

37. Positionnement final

Le site devient plus qu’un site vitrine.

Il constitue un :

Système automatisé d’acquisition, de qualification, d’estimation, de soumission, de réservation et de paiement pour les projets de marquage de stationnements commerciaux.

Parcours classique

Client → Adresse → Informations → Groupe Ferguson → Soumission ≤ 24 h → Acceptation → Rendez-vous → Paiement

Parcours Auto-Quote

Client → Adresse → Informations → Satellite → Zone → Auto-Quote → Acceptation → Rendez-vous → Paiement

⸻

38. Principe directeur

Le client donne les informations essentielles.

Groupe Ferguson peut préparer la soumission.

Ou le client peut utiliser l’Auto-Quote et continuer immédiatement.

L’objectif final est de permettre au client de passer de « Je veux faire marquer mon stationnement » à « Mon projet est réservé » avec le moins d’étapes et de friction possible.