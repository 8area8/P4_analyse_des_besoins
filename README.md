# P4_analyse_des_besoins

Documentation for a pizzeria's project.

on commence avec Impact Mapping et personas.

Donc pour reprendre, le client souhaite:

* une application qui gère toutes les pizzerias de l'entreprise
* Une meilleure automatisation des tâches pour aller plus vite
* Un suivit en temps réel des commandes
* Un suivit en temps réel des stocks d'ingrédients
* pouvoir passer des commandes sur internet (en plus du telephone et du sur place)
* payer en ligne (sinon au moment de la livraison)
* modifier ou annuler la commande tant qu'elle n'a pas commencé
* proposer un aide mémoire de recette aux pizzaiolos.

**ADMINISTRATION DES TOUTES LES PIZZERIAS:**

L'application communiquera avec une Map de type google map, qui répertoriera toute les pizzerias de l'entreprise. Le client (ou le vendeur qui entrera la commande du client) selectionnera une adresse qui sera testé dans cette map, et la pizzeria la plus proche (pour peu qu'elle ne soi pas trop lointaine) sera selectionné pour traiter sa commande.
Note: On doit entrer son adresse avant de selectionner sa pizza (pour connaître les stocks d'ingrédients de la pizzeria la plus proche). Si le client est trop loin de toute pizzeria, ou s'il le souhaite, il peut choisir de la retirer dans une pizzeria de son choix (le paiement se fera directement sur le site).

**MEILLEURE AUTOMATISATION DES TACHES:**

1. On va utiliser l'application pour tout type de commande (sur place, par téléphone et par internet). Les vendeurs qui recevront les commandes en direct ou par téléphone séléctionneront directement la commande du client via l'application, avec un profil vendeur spécifique qui permet d'insérer l'adresse du client à chaque commande.
1. Chaque commande passé (que ce soit par un client ou par un vendeur) est envoyé à la pizzeria voulue, et rejoint une "file d'attente des commandes" (```commande en attente```) consultable par les pizzaiolos de la pizzeria en question.
1. les pizzaiolos s'occupent de prendre les commandes (```commande en préparation```) de la file d'attente, de gérer les stocks d'ingrédients affichés (```en stock``` ou ```en rupture de stock```) et de valider les commandes lorsqu'elles sont prêtes (```commande prête à l'envoit```).
1. les livreurs consultent les commandes prêtes de leur pizzeria via un profil livreur spécifique, et séléctionnent les commandes prêtes à l'envoit qu'ils emportent (```commande en expedition```).
1. Enfin le client est livré, ce dernier paie s'il ne l'a pas déjà fait, et le livreur passe la commande en ```commande livré```. Elle est archivé.

**Un suivit en temps réel des commandes:**

Les commandes passeront par plusieurs états (```en attente```, ```prête à l'envoi```, etc.) que l'utilisateur pourra visualiser depuis l'application.
De plus, un temps d'attente approximatif sera donné lors de la validation de la commande. Il se basera sur la place de la commande de la liste d'attente et le temps moyen que met une commande à passer de son premier état ```en attente``` à son archivage (```commande livré```). Il distinguera les commandes à livrer chez le client de celles qui se livrent sur place (temps d'attente moindre).

**Un suivi en temps réel des stocks d'ingrédients:**

Les cuisiniers s'occuperont de la gestion des stocks de leurs ingrédients. Ils auront accès à la liste de tout leurs ingrédients, et pourront simplement desactiver (ou réactiver) un stock d'ingrédient depuis l'application.
Les clients et vendeurs pourront voir ces stocks en direct. Les pizzas disponibles seront influencés par ces stocks.
nNte: la gestion aurait pu être automatisé en fonction des commandes choisies (et d'un équivalent d'ingrédients par pizzas), mais les évènements ne sont pas aussi linéaires en cuisine qu'en informatique, et nous avons préféré le gérer à la main (boite d'ingrédient qui tombe, mauvaise commande, erreur de garniture, apport en ingrédients d'une autre pizzeria...)

**pouvoir passer des commandes par internet:**

En synthèse de ce qui a été dit précédemment, le client pourra selectionner sa pizza depuis l'application en spécifiant son adresse (une pizzeria lui sera automatiquement affecté) ou en selectionnant une pizzeria, s'il souhaite la retirer labas. Un compte d'utilisateur n'est pas requis pour valider la commande.

**pouvoir payer en ligne (ou au moment de la livraison):**

Le choix se fera lors de la finalisation de la commande. La commande possèdera un statut de paiement propre au choix de l'utilisateur (```payé``` ou ```en attente de paiement```), ce qui facilitera le travail du livreur.

**modifier ou annuler la commande tant qu'elle n'a pas commencé:**

La modification ou annulation de la commande pourra se faire tant que sont statut sera ```en attente```. Ce statut signifie que le pizzaiolo n'a pas commencé à la traiter.
Dans le cadre de l'annulation, si le client a payé sa pizza en ligne, un remboursement pourra se faire (avec peut être une commission en fonction du cout de remboursement par l'organisme bancaire utilisé?).
La modification d'une commande la retirera de la file d'attente. L'ajout ou le retrait d'ingrédient redéfiniera le prix total. Un surcout ou une différence sera demandé si l'utilisateur a déjà payé sa commande (payable directement aussi, ou avec le livreur).

**proposer un aide mémoire de recette aux pizzaiolos:**

Un aide mémoire des pizza sera disponible depuis l'application aux pizzaiolos, qui possèdent aussi un compte spécifique comme tout autre acteur de l'entreprise. L'ajout, la modification et la suppression se fera aussi très simplement, via le compte de l'administration générale des pizzeria (pour garder une cohérence d'ensemble). Si l'administrateur le souhaite, il peut donner ces droits aux pizzaiolos des différentes pizzeria, pour laisser place à une personnalisation des menus en fonction des pizzerias. Il conviendra aussi de donner les droits de modification des menus.

## A faire encore

* expliquer la démarche en cascade
* règles de gestion fonctionnelles
* processus de prise de commande, de la réservation à la livraison
* fonctionnalités du système (diagrammes de fonctionnalités)
* solution technique adaptée

Un document (PDF) de spécifications fonctionnelles comprenant :
les différents acteurs interagissant avec le futur système
le descriptif des fonctionnalités
les règles de gestion fonctionnelles
le cycle de vie des commandes
Un document (PDF, diaporama) – sans formalisme particulier mais un document à la présentation soignée – présentant rapidement la solution fonctionnelle et technique retenue ainsi que les arguments motivant ces choix.

DONC:

* je reformule mieux les spéc fonctionnelles
* j'ai définit succintement les méthodes employés pour chaque objectif
* je définie les acteurs
* je fais le diagramme de ccontext
* de packages
* diagrammes de cas d'utilisation + scénnarios de cas d'utilisation
* diagrammes d'états d'un commande