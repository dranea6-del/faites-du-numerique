# Journée de l’innovation : Faites du numérique ! — Halle aux sucres, Dunkerque

Carnet de bord interactif pour les participants de la journée du **mercredi 4 novembre 2026** (9 h – 16 h), organisée par la DRANE Hauts-de-France à la Halle aux sucres (Môle 1, 9003 route du Quai Freycinet 3, 59140 Dunkerque).

Application web **autonome** : un seul fichier `index.html`, aucune dépendance externe, aucun compte, aucune synchronisation. Elle fonctionne hors ligne une fois chargée et se consulte d’abord sur smartphone.

## Ce que fait l’application

- **Ma journée** : programme horaire. Le créneau en cours et le suivant sont mis en évidence d’après l’heure de l’appareil. Chaque créneau renvoie vers le plan et vers le carnet.
- **Plan** : schéma des niveaux N1, N2, N4 et N5 (entrée par le N2). Chaque espace ouvre une fiche (stand du matin ou atelier de l’après-midi, description, intervenants, places).
- **Mon carnet** : espaces vus, notes, « à retenir », choix de son atelier, trois champs de synthèse. Export par copie, téléchargement `.txt` ou impression.
- **Infos** : adresse, accès, repas, accessibilité, contact.

Les notes restent **sur l’appareil et dans le navigateur**. Il faut les exporter avant de vider les données du navigateur.

## Mode test

Ajoutez `?heure=HH:MM` à l’adresse pour simuler l’heure, par exemple `index.html?heure=11:20`.

## Modifier le contenu

Toutes les données sont dans l’objet `DATA`, au début du script de `index.html` : titre, date, niveaux, espaces (stands et ateliers), créneaux, infos pratiques, liens du dépôt. Aucune modification de la logique n’est nécessaire. Le plan se dessine tout seul : chaque niveau (`DATA.niveaux[…].rows`) liste ses rangées de tuiles, par exemple `{h:124, ids:["auditorium:2","cafe"]}` (`:2` = tuile deux fois plus large, `h` = hauteur facultative). Les tuiles remplissent toute la largeur du cadre ; un espace non listé est ajouté automatiquement en fin de niveau. Un champ `confirmer` affiche la mention « À confirmer » ; supprimez-le une fois l’information vérifiée.

## Charte graphique

Fond et cartes crème, bleu institutionnel pour les titres et les actions. Titres et textes en Georgia, menus et étiquettes en police à chasse fixe du système : aucune police à embarquer. Aucune photographie n’est intégrée. Le plan des niveaux est un schéma simplifié, non à l’échelle, et ne reproduit aucun plan d’architecte.

## Affichage

Le site s’adapte à tous les écrans. Sur smartphone, une colonne et une barre à quatre entrées. Sur tablette, les cartes et les infos passent sur deux colonnes. Sur ordinateur (à partir de 960 px), la barre affiche aussi le nom de la DRANE et la date, la carte « en ce moment » reste fixe à gauche du programme, et le plan s’affiche à côté de la légende et de la liste des espaces.

## Navigation

Une barre flottante en haut propose quatre entrées : Accueil, Plan, Carnet, Infos. Sur les pages Plan, Carnet et Infos, un bouton « Accueil » remplace le grand titre et ramène à la page d’accueil. Toucher une entrée déroule un panneau de cartes : créneaux en cours et à venir, les quatre niveaux, l’état du carnet, les infos clés. Toucher une carte ouvre la page à l’endroit voulu ; le bouton en haut du panneau ouvre la section. Le contenu des panneaux se règle dans la fonction `menuData` du script. La touche Échap ou un toucher en dehors referme le panneau.

## Informations à confirmer

- Adresse du dépôt Forge et du suivi des problèmes (champs `depot` et `suivi`).
- Lieu du repas « Bar à pâtes » et lieu de la clôture.
- Descriptions des stands Nird, Idée, Ted-I, Tralalère et Jeu Cyber-duel, et des ateliers Vibecoding et RVRC.
- Matériel à prévoir pour les ateliers autres que Ludicisation.
- Accessibilité, restaurant et patio (fiche publique du lieu).
- La légende du plan d’origine indique « 3 niveaux » mais en cite 4 (N1, N2, N4 et N5) : l’application affiche 4 niveaux.

## Sources

- Programme et plan de l’organisation (DRANE Hauts-de-France), fichier des ateliers.
- Fiche d’accessibilité Acceslibre : https://acceslibre.beta.gouv.fr/app/59-dunkerque/a/musee/erp/la-halle-aux-sucres/
- LinuxFr (démarche NIRD et PrimTux), fiches du jeu Cyber-duel (Philibert, Cyber Wargame), offre d’emploi du GIP ViaPro (programme Idée).

## Auteur, licence et IA

DRANE de Lille (drane@region-academique-hdf.fr), créé avec l’aide de l’IA (Claude, Anthropic). Le contact affiché dans le pied de page se modifie dans `DATA.contact`. Les textes issus de sources publiques ont été reformulés et doivent être relus avant diffusion.

Licence proposée : [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.fr) (à confirmer).
