# Schéma de données pour le comptage des mobilités - Fichier measure

Spécifications du fichier d'échange relatif aux comptages des mobilités : fichier measure.

Le schéma de comptage des mobilités est structuré en trois notions distinctes : les sites, les channels, et les mesures.
Chacune de ces notions est retranscrite dans son propre fichier :
les sites vont dans un fichier `sites.csv` avec une ligne par site les channels dans un fichier `channels.csv` (idem),les mesures dans un fichier `measures.csv` (idem).

Ce schéma est spécifique à la notion de measure.
Le fichier measure contient les données de comptage. Ce fichier est dit “dynamique” car les données seront amenées à être fréquemment mises à jour selon le pas de temps ou la fréquence de rafraîchissement que le producteur définira en amont.
Les données fournies le sont soit en "temps-réel", soit a posteriori.
Le fichier contiendra autant de ligne que de comptage par créneau temporel ou par pas de temps.

## Finalité

Ce schéma permet d'estimer la fréquentation d'infrastructures grâce à des données dynamiques de comptage.
Il doit être associé au schéma "site" et "channel" de comptage des mobilité. Il ne peut être réutilisé sans ces fichiers.

## Format de fichier

Les fichiers seront publiées au format CSV UTF-8 avec séparateur virgule ",". Certains champs sont obligatoires et d'autres optionnels. Les champs obligatoires doivent être complétés. Les champs optionnels peuvent être vides si la donnée n’est pas disponible. La colonne doit toutefois être présente.

## Publication

Les producteurs pourront :

- publier directement sur data.gouv.fr ;
- publier sur un portail local ou régional et s'assurer que les données publiées sont bien moissonnées et référencées sur data.gouv.fr.
Nous préconisons aux producteurs de données de publier leurs fichiers avec la règle de nommage suivante : comptagemobilites_measure_nom.csv avec nom étant le nom de la collectivité productrice des données, par exemple comptagemobilite_measure_Baix.csv

Nous recommandons de publier le fichier measure dans le même jeu de données que les fichiers site et channel. Ces trois fichiers s'articulent entre eux par des identifiants.

## Utilisation de notre outil d'aide à la saisie et du validateur

Pour être guidé pas à pas, merci de vous rendre sur la [documentation officielle de transport.data.gouv.fr](https://doc.transport.data.gouv.fr/producteurs/comptage-des-mobilites), Point d'accès national aux données de transport.

Pour faciliter le remplissage des données, Etalab met à disposition un générateur CSV conforme au schéma de données, vous permettant de remplir les différents champs demandés. Cet outil vous permet de vous assurer que les données que vous remplissez sont au bon format. Pour l'utiliser, rendez-vous sur [https://publier.etalab.studio](https://publier.etalab.studio), vous pourrez alors publier votre fichier à partir d'un :

- CSV déjà existant ;
- formulaire ;
- tableur (encore en expérimentation).

Une fois vos données chargées ou remplies, un formulaire vous proposera de les publier sur data.gouv.fr.

Avant de publier vos données, vous pouvez vérifier qu'elles sont valides depuis [le validateur Validata](https://validata.fr/) en choisissant le schéma associé au fichier dans la partie "schema.data.gouv.fr".

## Fichiers d'exemple
Deux fichiers d'exemples sont fournis pour ce schéma :

- un fichier d'exemple `exemple-valide.csv` avec tous les champs remplis ;
- un fichier d'exemple `exemple-valide-eco-compteur.csv` élaboré par Eco-Compteur dont certaines valeurs optionnelles ne sont pas renseignées.

## Notes techniques pour contribuer à ce schéma

Ce schéma s'appuie sur [TableSchema](https://specs.frictionlessdata.io/table-schema/). Pour le modifier, il peut être utile en particulier de se référer à la [spécification des descripteurs de champs](https://specs.frictionlessdata.io/table-schema/#field-descriptors).
