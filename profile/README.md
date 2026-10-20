<p align="center">
  <img src="https://raw.githubusercontent.com/Sonar-l10n-FR/.github/main/assets/logo.svg" alt="Pack de traduction française" width="120" />
</p>

<h1 align="center">Pack de traduction française pour SonarQube™</h1>

<p align="center">
  <strong>L'interface de SonarQube™ en français, réglages et analyseurs compris.</strong><br/>
  Un projet communautaire et libre, sous licence LGPL-3.0.
</p>

<p align="center">
  <a href="https://github.com/Sonar-l10n-FR/sonar-l10n-fr/releases">Télécharger</a> &bull;
  <a href="https://github.com/Sonar-l10n-FR/sonar-l10n-fr/issues">Signaler une erreur</a> &bull;
  <a href="https://github.com/Sonar-l10n-FR/sonar-l10n-fr">Code source</a>
</p>

---

## Le projet

Le pack `l10nfr` traduit SonarQube™ en français. Il couvre l'interface web, les écrans d'administration avec les libellés de leurs réglages, et les paramètres de règles de certains analyseurs. Il s'installe comme un plugin, et SonarQube™ l'utilise dès que le navigateur demande le français.

Sur une Community Build 26.10, il traduit **8 297 des 8 438 messages** que sert l'interface. Les 141 autres s'écrivent de la même façon en français (noms de produits, sigles, « Description », « Version ») ou ne sont pas du texte affiché.

### Ce qu'aucun pack de langue ne peut traduire

Quelques textes échappent à toute traduction, parce que SonarQube™ ne les fait pas passer par son catalogue :

- **Les tableaux de bord intégrés.** « Project health dashboard » et ses sections sont lus tels quels dans le serveur.
- **Certains titres de widgets.** Ils sont assemblés morceau par morceau dans l'ordre de l'anglais, d'où « Sécurité Problèmes » pour « Security Issues ».
- **Le reste.** Les textes écrits en dur dans l'interface, et les données en base comme les descriptions de groupes.

Les signaler reste utile : ce sont des limites à remonter à SonarSource, et nous les documentons.

---

## Installation

1. Téléchargez le jar de la [dernière release](https://github.com/Sonar-l10n-FR/sonar-l10n-fr/releases/latest) et vérifiez son empreinte :
   ```sh
   sha256sum -c sonar-l10n-fr-plugin-<version>.jar.sha256
   ```
2. Copiez-le dans `extensions/plugins/` (dans l'image Docker : `/opt/sonarqube/extensions/plugins/`). Retirez l'éventuelle version précédente du pack : avec deux versions d'un même plugin, le serveur ne démarre pas.
3. Redémarrez SonarQube™.

Le Marketplace (Administration > Marketplace) propose encore la version 10.0.0 de 2023, en attendant que son entrée pointe vers ce dépôt.

### Compatibilité

| Version du pack | SonarQube™ Community Build |
|---|---|
| 26.10.0 | 26.10 |

Chaque version du pack suit le catalogue d'une version précise de SonarQube™. Elle se charge aussi sur d'autres versions, le plugin n'exigeant que l'API 9.14, mais elle n'est vérifiée que sur celle-ci.

---

## D'où vient ce dépôt

Le pack existe depuis 2011. Il a d'abord été hébergé par SonarSource, puis maintenu par la communauté, en dernier lieu par jycr sur son compte personnel. En octobre 2026, jycr a passé la main et transféré le dépôt d'origine dans cette organisation, avec son historique, ses issues et ses releases ([#47](https://github.com/Sonar-l10n-FR/sonar-l10n-fr/issues/47)). Les anciens liens `jycr/sonar-l10n-fr` redirigent ici.

Le pack vit désormais dans une organisation plutôt que dans un compte personnel : la maintenance peut changer de mains sans que le projet change d'adresse.

---

## Contribuer

**Une traduction fausse, un écran resté en anglais :** ouvrez une [issue](https://github.com/Sonar-l10n-FR/sonar-l10n-fr/issues), avec si possible une capture et l'adresse de la page.

**Proposer une correction :**

- **Où sont les traductions :** dans `src/main/resources/org/sonar/l10n/`. Ces fichiers sont en ISO-8859-1 (voir `.gitattributes`).
- **Ce que vérifie le harnais de tests :** ce qu'un relecteur oublierait, à savoir l'apostrophe typographique (’), l'espace insécable avant `:` `;` `!` `?`, l'écriture épicène, et des arguments identiques à ceux de l'anglais.
- **Lancer le harnais :** `tools/mvn.sh clean verify`. Seul Docker est nécessaire.

| Dépôt | Contenu |
|---|---|
| [**sonar-l10n-fr**](https://github.com/Sonar-l10n-FR/sonar-l10n-fr) | Le plugin `l10nfr` : les traductions, l'outillage qui les synchronise sur chaque version de SonarQube™, le harnais de tests |

---

<p align="center">
  <sub>SonarQube™ et Sonar™ sont des marques déposées de SonarSource SA. Ce projet n'est pas un produit Sonar™ : il n'est ni affilié à SonarSource, ni approuvé par elle.</sub>
</p>
