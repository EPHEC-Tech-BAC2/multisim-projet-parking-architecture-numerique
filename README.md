# Projet Parking — Architecture systèmes numériques et Électronique

Projet réalisé à l'EPHEC-Tech (2AU, 2025-2026), à quatre : **ELHAMAYDA Amer**, **EL YAZAMI Yassine**, **SEYE Mouhammed**, **SHEIKH Abdul Moize**.

## Le projet

Conception d'un système électronique numérique gérant le nombre de places disponibles dans un parking : le compteur diminue à chaque entrée de véhicule et augmente à chaque sortie, avec affichage sur 7 segments. Le projet a été entièrement réalisé et simulé sous **Multisim**, les capteurs réels étant simulés par des switchs.

## Fonctionnement du circuit

- **Détection** : deux comparateurs **LM339AJ** transforment l'action des switchs (entrée/sortie véhicule) en signaux logiques exploitables.
- **Comptage** : un compteur/décompteur **74193N** incrémente ou décrémente la valeur (de 4 à E en hexadécimal), pilotée par les entrées UP/DOWN.
- **Stabilisation** : un registre **74LS373N** fige la valeur binaire avant affichage, pour limiter l'effet des rebonds mécaniques des switchs.
- **Affichage** : un afficheur 7 segments hexadécimal affiche en continu le nombre de places disponibles.
- **Gestion des limites** : un comparateur numérique **74S85D** compare la valeur du compteur à une référence minimale ; combiné à des portes logiques (AND, NAND, NOT), il bloque la décrémentation une fois la limite atteinte.
- **Signalisation** : deux transistors NPN (**2N2222A**) pilotent une LED verte (parking disponible) et une LED rouge (parking plein / accès bloqué).

## Résultats

Incrémentation jusqu'à la valeur maximale (E), décrémentation bloquée à la valeur minimale (4), affichage stable et LED cohérentes avec l'état du parking.

## Pistes d'amélioration

- Corriger la logique de blocage pour un comportement parfaitement symétrique
- Remplacer les switchs par de vrais capteurs (infrarouge, ultrasons)
- Ajouter un second afficheur 7 segments pour aller jusqu'à 99 places
- Réalisation physique du circuit

## Logiciel

- Multisim (simulation de circuits électroniques numériques)

## Contenu du dépôt

- `simulation-multisim/` : fichier de simulation Multisim du circuit
- `rapport/` : rapport complet du projet (composants, dimensionnement, résultats)