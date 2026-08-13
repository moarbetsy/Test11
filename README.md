# GROUPE FERGUSON
## Plan devis technique final
**Site :** GroupeFerguson.ca  
**Projet :** Système d'estimation, Auto-Quote, soumission, réservation et paiement pour le marquage de stationnements commerciaux

---

# 1. Objectif
Créer un système Web permettant à un client de :
**S'identifier → Entrer l'adresse → Décrire le projet → Choisir son parcours → Obtenir une soumission ou une Auto-Quote → Réserver → Payer**

Le système intègre la gestion des contraintes réelles du marquage (météo, préparation de surface, accès au site, frais minimums et horaires de nuit/fin de semaine).

Deux parcours sont disponibles :
1. **Soumission Groupe Ferguson** : l'équipe prépare la soumission et communique avec le client dans les 24 heures.
2. **Auto-Quote** : le client utilise la carte satellite, obtient instantanément une quote, réserve sa date et paie en ligne.

---

# 2. Parcours général
```text
ACCUEIL
   ↓
CLIENT
   ↓
ADRESSE DU PROJET
   ↓
NOMBRE DE PLACES
   ↓
SYMBOLES & PRÉPARATION DE SURFACE
   ↓
TYPE DE STATIONNEMENT & HORAIRES
   ↓
TYPE DE TRAVAUX
   ↓
CHOIX DU PARCOURS
   ├───────────────┐
   ↓               ↓
SOUMISSION 24 H   AUTO-QUOTE
   ↓               ↓
GROUPE FERGUSON  SATELLITE
   ↓               ↓
SOUMISSION       ZONE DE TRAVAUX
   │               ↓
   │           SUPERFICIE
   │               ↓
   │           CALCUL DU PRIX (Prix min. + Surcharges)
   │               ↓
   │             QUOTE (Validité 14 jours)
   │               ↓
   └───────→ ACCEPTATION
                   ↓
               RÉSERVATION
                   ↓
         PRÉPARATION DU SITE (Clause déplacement à vide)
                   ↓
                PAIEMENT
                   ↓
              CONFIRMATION
                   ↓
           RAPPELS & GESTION MÉTÉO
```

---

# 3. Accueil

Titre

Marquage et traçage de stationnements commerciaux

Action principale

Obtenir une soumission

Option secondaire

Obtenir une Auto-Quote

Le site présente rapidement les services de Groupe Ferguson sans imposer la carte à tous les visiteurs.

---

# 4. Étape 1 — Client

Type de client

* Entreprise / Commercial
* Gestionnaire / Copropriété
* Particulier

Informations

* Nom
* Nom de l’entreprise, si applicable
* Téléphone (compatible SMS)
* Courriel

Ces informations constituent le dossier client. Dès cette étape, un dossier brouillon est sauvegardé pour permettre la relance en cas d'abandon.

---

# 5. Étape 2 — Adresse du projet

Question

Quelle est l’adresse du stationnement à marquer?

Le système :

* valide l’adresse;
* normalise l’adresse;
* récupère latitude et longitude;
* crée le projet;
* calcule automatiquement la distance depuis Groupe Ferguson.

---

# 6. Calcul automatique de la distance

Le système calcule la distance entre :

Point de référence Groupe Ferguson

et

Adresse du projet

Lorsque cette distance sert à déterminer des frais de déplacement, utiliser de préférence la distance routière.

Données conservées

distance_km
source_du_calcul
date_du_calcul
zone_tarifaire

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

Les zones et tarifs doivent être configurables dans l’administration.

---

# 7. Étape 3 — Nombre de places

Question

Combien de places de stationnement?

[ __________ ]

Cette information est conservée dans le projet et réutilisée automatiquement dans la soumission et l’Auto-Quote.

---

# 8. Étape 4 — Symboles

Question

Quels symboles et travaux de préparation devez-vous faire exécuter?

Symbole / Service	Quantité / Option
PMR	[ ]
Flèches	[ ]
Réservé	[ ]
Recharge électrique	[ ]
Hachurage / Autre	[ ]
Balayage / Nettoyage mécanique	○ Oui  ○ Non
Lavage haute pression	○ Oui  ○ Non
Effacement / Meulage d'anciennes lignes	○ Oui  ○ Non

Bouton :

+ Ajouter un symbole

Option :

Aucun symbole

---

# 9. Étape 5 — Type de stationnement

○ Stationnement extérieur
○ Stationnement sous-terrain
○ Extérieur + sous-terrain

Si sous-terrain

Afficher :

Hauteur libre maximale [ ___ ] mètres

Photos du stationnement (Optionnel) : [ Téléverser des photos ]

Commentaires / particularités

Exemples :

* accès particulier;
* hauteur limitée;
* circulation;
* contraintes;
* heures d’accès.

Contraintes d'exécution (Horaires)

○ Heures régulières (De jour, Lundi au Vendredi)
○ Hors-heures (De nuit ou Fin de semaine - Surcharge applicable)

---

# 10. Étape 6 — Type de travaux

○ Nouveau marquage
○ Repeinture
○ Nouveau marquage + repeinture

---

# 11. Choix du parcours

Une fois les informations de base recueillies, présenter deux options.

Option A — Soumission Groupe Ferguson

Recevoir ma soumission

Nous préparerons votre soumission et communiquerons avec vous dans les 24 heures.

Le client n’a pas besoin d’utiliser la carte.

Les informations sont transmises directement à Groupe Ferguson.

Option B — Auto-Quote

Obtenir mon Auto-Quote maintenant

Dessinez votre zone de travaux sur la carte et obtenez votre quote instantanément.

La carte satellite apparaît uniquement si le client choisit cette option.

---

# 12. Parcours — Soumission 24 heures

Client
↓
Adresse
↓
Places
↓
Symboles & Préparation
↓
Type de stationnement & Horaires
↓
Type de travaux
↓
Distance
↓
Dossier Groupe Ferguson
↓
Préparation de la soumission
↓
Envoi au client

Confirmation

Votre demande a été reçue. Groupe Ferguson préparera votre soumission et communiquera avec vous dans les 24 heures.

Le délai doit être appliqué conformément aux heures de service et aux conditions commerciales de Groupe Ferguson.

---

# 13. Parcours — Auto-Quote

Lorsque le client choisit Auto-Quote, afficher automatiquement la carte satellite centrée sur l’adresse fournie.

---

# 14. Carte satellite

Instruction

Tracez approximativement la zone à travailler.

Le client dessine le périmètre.

Le système calcule automatiquement :

* superficie;
* périmètre;
* coordonnées;
* zone de travaux.

Option d'assistance UX / Mobile :

Si la carte satellite est masquée (arbres, neige, mauvaise résolution) ou difficile à tracer sur mobile, un bouton permet de basculer vers le parcours Soumission 24 h sans perdre les données déjà saisies.

Le client n’a pas besoin de mesurer lui-même la superficie.

---

# 15. Moteur Auto-Quote

Le moteur combine toutes les données :

Client
+
Adresse
+
Distance
+
Nombre de places
+
Symboles & Préparation
+
Type de stationnement & Horaires
+
Type de travaux
+
Zone dessinée
+
Superficie
+
Règles tarifaires (Prix minimum & Surcharges)
=
AUTO-QUOTE

---

# 16. Moteur de prix

Les paramètres doivent être configurables par Groupe Ferguson.

Paramètres possibles

* tarif au m²;
* tarif par place;
* prix par symbole;
* prix préparation de surface (nettoyage, effacement);
* type de travaux;
* supplément sous-terrain;
* supplément travaux hors-heures (nuit/fin de semaine);
* frais de déplacement;
* zones kilométriques;
* prix minimum par déplacement (prix plancher, ex: 350 $);
* frais supplémentaires;
* taxes;
* rabais;
* durée de validité (ex: 14 jours).

Les tarifs commerciaux ne doivent pas être codés directement dans l’interface.

---

# 17. Présentation de l’Auto-Quote

Exemple :

Votre Auto-Quote

3 850 $

Validité : Cette estimation est garantie pendant 14 jours.

Afficher le détail pertinent :

* travaux;
* nombre de places;
* symboles et nettoyage;
* superficie;
* type de stationnement et horaire sélectionné;
* distance;
* frais et prix minimum appliqué si applicable;
* taxes.

Lorsque l’incertitude est importante, le système peut afficher une fourchette :

3 600 $ – 4 100 $

Avis

Cette Auto-Quote est basée sur les informations fournies et la zone approximativement sélectionnée. Groupe Ferguson se réserve le droit d'ajuster le prix si les conditions réelles du projet diffèrent des informations fournies.

---

# 18. Acceptation

Bouton :

ACCEPTER L’AUTO-QUOTE

Le système enregistre :

* numéro du projet;
* version de la quote;
* montant;
* données utilisées;
* date d'expiration;
* date;
* heure;
* client.

Statut :

Auto-Quote acceptée

---

# 19. Réservation

Après acceptation :

CHOISIR MON RENDEZ-VOUS

Le client voit les disponibilités configurées par Groupe Ferguson. Le créneau est verrouillé pendant 15 minutes durant la prise de rendez-vous.

Il sélectionne :

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

Les doubles réservations doivent être bloquées.

---

# 20. Préparation du site

Avant la confirmation et le paiement :

Veuillez vous assurer qu’aucun véhicule ne se trouve dans la zone des travaux au moment de notre arrivée.

Confirmation obligatoire

☐ Aucun véhicule ne sera présent dans la zone de travaux.
☐ La zone sera libre d'obstacles.
☐ L'accès au stationnement sera disponible.
☐ Les restrictions particulières ont été communiquées.
☐ J'accepte qu'un frais de déplacement à vide (250 $) s'applique si les travaux ne peuvent être exécutés à notre arrivée en raison d'un site non libéré.

---

# 21. Paiement

Après l’acceptation et la réservation :

Option 1 — Dépôt

5 % de rabais

Le client paie le dépôt applicable (ex: 30% ou 50%). La carte est conservée de manière sécurisée pour le solde.

Option 2 — Paiement complet

10 % de rabais

Le client paie la totalité du projet.

Les rabais ne sont pas cumulables.

Le système affiche avant le paiement :

Prix original
Rabais
Montant à payer
Solde éventuel

---

# 22. Stripe

Stripe est utilisé pour traiter les paiements.

Le système conserve :

* identifiant de transaction;
* identifiant client Stripe (`setup_future_usage` pour prélever le solde);
* projet;
* type de paiement;
* montant;
* rabais;
* statut;
* date;
* solde.

La confirmation du paiement et le calcul du montant doivent être effectués et validés obligatoirement côté serveur.

Les données sensibles de carte ne doivent pas être stockées directement par Groupe Ferguson.

---

# 23. Confirmation finale

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

Une confirmation est envoyée au client (Courriel + SMS).

---

# 24. Rappels & Gestion Météo

Confirmation

Immédiatement après la réservation.

Rappel avant les travaux

Rappeler (J-2 et J-1) :

* aucun véhicule dans la zone;
* zone dégagée;
* accès disponible;
* obstacles retirés;
* restrictions communiquées.

Gestion des intempéries (Météo)

En cas de pluie ou températures non conformes :

* l'administration passe la journée en « Annulée - Météo »;
* le client reçoit automatiquement un SMS/Courriel avec un lien prioritaire pour rechoisir une date dans le calendrier.

---

# 25. Administration Groupe Ferguson

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
Projets reportés (Météo)
Projets terminés

---

# 26. Fiche projet

Toutes les données doivent être regroupées dans une seule fiche.

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
- Distance
- Type de stationnement (Hauteur sous-terrain)
- Contrainte horaire (Jour / Nuit / Fin de semaine)
- Type de travaux
- Nombre de places
TRAVAUX
- Symboles & Quantités
- Préparation de surface (Balayage, Meulage)
- Zone
- Superficie
- Commentaires
- Photos téléversées
VENTE
- Estimation
- Auto-Quote (Version, Date expiration, Prix min. appliqué)
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
HISTORIQUE / LOGS
- Actions
- Dates
- Versions

---

# 27. Statuts

Soumission classique

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
PLANIFIÉ (ou REPORTÉ MÉTÉO / SITE NON DÉGAGÉ)
        ↓
TRAVAUX
        ↓
TERMINÉ

Auto-Quote

AUTO-QUOTE
    ↓
ACCEPTÉE
    ↓
RENDEZ-VOUS
    ↓
PAIEMENT
    ↓
PLANIFIÉ (ou REPORTÉ MÉTÉO / SITE NON DÉGAGÉ)
    ↓
TRAVAUX
    ↓
TERMINÉ

---

# 28. Calendrier

L’administration doit permettre de configurer :

* jours disponibles;
* heures disponibles;
* durée des travaux;
* temps tampon;
* journées bloquées;
* annulations météo en masse;
* vacances;
* capacité quotidienne (m² maximums par jour);
* disponibilités exceptionnelles.

---

# 29. Notifications

Client

* demande reçue;
* soumission disponible;
* Auto-Quote générée;
* Auto-Quote acceptée;
* rendez-vous confirmé;
* rappel pré-travaux;
* alerte remise à plus tard pour météo (avec lien de re-planification);
* paiement confirmé;
* projet confirmé.

Groupe Ferguson

* nouvelle demande;
* demande à traiter;
* Auto-Quote acceptée;
* soumission acceptée;
* nouveau rendez-vous;
* paiement;
* problème d'accès terrain (site non libéré);
* annulation;
* modification.

---

# 30. Calcul de distance

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
Zone tarifaire
        ↓
Frais éventuels

Données conservées :

distance_km
source_du_calcul
date_du_calcul
zone_tarifaire
frais_appliqués

Le calcul associé à une Auto-Quote ou à une soumission doit être conservé afin de pouvoir reproduire le prix.

---

# 31. Base de données

Client

id
type_client
nom
entreprise
courriel
telephone
date_creation

Projet

id
client_id
adresse
latitude
longitude
distance_km
zone_tarifaire
type_stationnement
hauteur_sous_terrain
contrainte_horaires
type_travaux
nombre_places
commentaires
statut

Projet_Photos

id
project_id
url_photo
date_upload

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
prix_preparation
surcharge_horaire
frais_distance
frais_minimum_applique
total
version
date_expiration
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
stripe_customer_id
type_paiement
montant_original
rabais
montant_paye
solde
statut
date

Projet_Logs

id
project_id
action
auteur
date

---

# 32. Sécurité

Prévoir :

* HTTPS;
* authentification sécurisée;
* contrôle des accès;
* protection anti-spam;
* validation serveur (calcul des prix et paiements côté serveur uniquement);
* validation des fichiers / photos téléversés;
* sauvegardes;
* journalisation;
* protection des renseignements personnels;
* validation serveur des paiements Stripe.

---

# 33. Expérience mobile

Le système doit être mobile-first.

Priorités

1. Peu de champs.
2. Grandes zones tactiles.
3. Progression claire.
4. Aucune répétition.
5. Carte simple avec bouton de secours si dessin difficile.
6. Chargement rapide.
7. Une action principale par écran.

---

# 34. Principe de réduction de friction

Le client ne doit jamais avoir à :

* mesurer son stationnement;
* calculer les kilomètres;
* rechercher deux fois son adresse;
* ressaisir le nombre de places;
* ressaisir les symboles;
* appeler pour connaître les disponibilités lorsqu’il utilise l’Auto-Quote.

Principe

Une information saisie une fois est réutilisée partout.

---

# 35. Architecture fonctionnelle

                    GROUPEFERGUSON.CA
                             │
                             ▼
                          CLIENT (Sauvegarde brouillon)
                             │
                             ▼
                    INFORMATIONS CLIENT
                             │
                             ▼
                         ADRESSE
                             │
                             ▼
                    CALCUL DE DISTANCE
                             │
                             ▼
                    NOMBRE DE PLACES
                             │
                             ▼
               SYMBOLES & PRÉPARATION SURFACE
                             │
                             ▼
             TYPE STATIONNEMENT & HORAIRES
                             │
                             ▼
                     TYPE DE TRAVAUX
                             │
                             ▼
                  ┌──────────┴──────────┐
                  │                     │
                  ▼                     ▼
             SOUMISSION             AUTO-QUOTE
                24 H                    │
                  │                     ▼
                  │                SATELLITE (Option secours mobile)
                  │                     │
                  │                     ▼
                  │                    ZONE
                  │                     │
                  │                     ▼
                  │                SUPERFICIE
                  │                     │
                  │                     ▼
                  │           CALCUL PRIX (Prix min/Surcharges)
                  │                     │
                  │                     ▼
                  │            QUOTE (Valide 14j)
                  │                     │
                  └──────────┬──────────┘
                             ▼
                         ACCEPTATION
                             │
                             ▼
                         CALENDRIER
                             │
                             ▼
              PRÉPARATION SITE (Dry-run fee)
                             │
                             ▼
                      STRIPE (Paiement/Dépôt)
                             │
                             ▼
                        CONFIRMATION
                             │
                             ▼
                  RAPPELS & GESTION MÉTÉO

---

# 36. Positionnement

Le système devient un outil de vente et de gestion complet :

Système automatisé d’acquisition, de qualification, d’estimation, de soumission, de réservation, de gestion météo et de paiement pour les projets de marquage de stationnements commerciaux.

Parcours classique

Client
→ Adresse
→ Places
→ Symboles & Préparation
→ Type de stationnement & Horaires
→ Travaux
→ Groupe Ferguson
→ Soumission ≤ 24 h
→ Acceptation
→ Rendez-vous
→ Engagements site
→ Paiement

Parcours Auto-Quote

Client
→ Adresse
→ Places
→ Symboles & Préparation
→ Type de stationnement & Horaires
→ Travaux
→ Satellite
→ Zone
→ Superficie
→ Auto-Quote
→ Acceptation
→ Rendez-vous
→ Engagements site
→ Paiement

---

# 37. Principe directeur final

Le client fournit les informations essentielles.

Groupe Ferguson peut préparer la soumission dans les 24 heures.

Ou le client peut utiliser l’Auto-Quote pour obtenir immédiatement son prix garanti.

Une fois accepté, le client s'engage sur la préparation du site, réserve sa date et effectue son paiement en ligne.

En cas de mauvaise météo, le système gère automatiquement le report du rendez-vous.

L’objectif est de transformer le plus simplement possible :

« Je veux faire marquer mon stationnement »

en

« Mon projet est réservé, planifié et confirmé. »