# FFTT Api — Fork USFAV

Fork du projet [alamirault/fftt-api](https://github.com/alamirault/fftt-api) avec quelques ajustements spécifiques au club.  
Les éventuels bugs / améliorations génériques seront proposés sur le repo d'origine.

### Différences avec l'upstream

- Ajout de `TypeLicenceEnum::Arbitre` (`'A'`)
- Correction : retour vide quand la liste des parties est vide ou malformée
- Correction : calcul des points virtuels robuste quand le nom adverse est absent
- Contrainte PHP relevée à `^8.1` (cohérence avec l'usage des enums natifs)

### Prérequis

- PHP >= 8.1
- Extensions : `simplexml`, `json`

### Installation

```bash
composer require jarash/fftt-api
```

> Ce package remplace `alamirault/fftt-api` à la même version (`replace: self.version`).

### Exemple d'utilisation

```php
<?php

use Alamirault\FFTTApi\Service\FFTTApi;

require __DIR__ . '/vendor/autoload.php';

$ffttApi = new FFTTApi('MON_IDENTIFIANT', 'MA_CLE');

// Liste des joueurs d'un club
$joueurs = $ffttApi->getJoueursByClub('00850001');

// Points virtuels d'un joueur
$virtualPoints = $ffttApi->getVirtualPoints('123456A');
```

### Fonctionnalités disponibles

- Liste des organismes
- Liste et détail des clubs (par département ou par nom)
- Liste et détail des joueurs (par club, par nom)
- Classement et historique d'un joueur
- Parties validées et non validées d'un joueur
- Points virtuels d'un joueur
- Équipes d'un club, classement de poule
- Liste et détail des rencontres
- Liste des actualités

