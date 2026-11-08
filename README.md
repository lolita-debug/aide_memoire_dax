# Aide-mémoire DAX (Power BI, format PBIP)
📊 **Présentation en 10 diapositives** : [Comprendre le rapport et le faire tourner](Aide_memoire_DAX_comprendre_le_rapport.pptx)


Un rapport Power BI pour apprendre et réviser le langage DAX. Il contient :
- **Guide des fonctions** : la liste des fonctions DAX, avec une fiche détaillée pour chacune et une page d'export.
- **Top 25** : une sélection indicative des fonctions à connaître en priorité.
- **12 fiches pratiques** : pour chaque fonction, la formule, ce qu'il faut retenir et le résultat sur des données fictives.
- **Sources et contrôles** : d'où viennent les données, et la cohérence entre les sources.
- **Gabarits (copie-moi)**, page masquée : des modèles de cartes KPI, de graphique et de tableau, à copier dans ses propres pages.

Toutes les données d'exemple (produits, marques, ventes) sont **fictives**.

## Ouvrir le rapport

1. Ouvrir `Dax_Reference_Cheat_Sheet.pbip` avec Power BI Desktop, dans une version récente qui gère le format PBIP/PBIR.
2. **Actualiser.** Le rapport est livré sans données. La première actualisation lit la documentation Microsoft Learn (fr-fr), une page par fonction, et prend plusieurs minutes.
   - Pour un premier aperçu rapide : Transformer les données › paramètre `ParamScraperDetails` = `false`.
3. Dans Desktop, il faut **Ctrl + clic** sur les boutons.
4. Pour afficher la page masquée Gabarits : clic droit sur son onglet › Afficher.

## Classeur Excel `COMMANDES_DAX.xlsx` (facultatif)

Le dépôt contient un classeur de notes personnelles sur **223 fonctions DAX** : usage, exemples commentés, remarques pratiques et une **matrice d'usage** (utilisable en colonne calculée, table calculée, mesure, calcul visuel : ✔ oui, ❗ avec précaution, ❌ non).

| Onglet | Rôle |
|---|---|
| `Data_Dax` (tableau `DATA_DAX`) | Lu par le rapport : rubrique « Fiche maison » du Guide, ligne « ex : » du Top 25, page Export, taux de couverture |
| `DAX_RELATIONS` | Consultation seule : fonctions de relations (RELATED, USERELATIONSHIP…) avec exemples. Non lu par le rapport |

**Brancher le classeur** : Transformer les données › Paramètres › `ParamCheminExcel` › coller le chemin complet du fichier sur votre poste (par exemple `C:\Users\vous\Documents\COMMANDES_DAX.xlsx`), puis Actualiser.

**Sans classeur, le rapport fonctionne** : les rubriques « Fiche maison » affichent alors « — ».

Pour ajouter vos propres notes : ajoutez des lignes au tableau `DATA_DAX` en gardant les mêmes colonnes. La colonne `Fonction DAX` doit contenir le nom exact de la fonction. Dans les colonnes de la matrice, utilisez uniquement ✔, ❗ ou ❌.

Les exemples marqués 🔧 sont adaptés de la documentation Microsoft Learn (CC BY 4.0).

## Modifier une fiche pratique

Tout se fait dans Power BI Desktop, sans outil externe.

| Je veux… | Où |
|---|---|
| Changer une formule | Modifier la **mesure** (dossier « Exemples »), puis clic droit sur la table **Exemples** › Actualiser les données |
| Changer les mesures affichées dans une fiche | Requête **Exemples**, colonne `Mesures` : noms exacts, séparés par `\|` |
| Changer le texte « à retenir » | Requête **Exemples**, colonne `Retenir` : puces séparées par ` \| `, code entre `{{` et `}}` |

## Thème D2 : sombre et accessible

Le fichier `Theme_D2_Sombre_Accessible.json` est livré **à part, à la racine du zip**. Il est réutilisable dans n'importe quel rapport : Affichage › Thèmes › Parcourir les thèmes.

| Ce que le thème règle tout seul | Ce qu'il ne peut pas régler |
|---|---|
| Police Calibri, couleurs, fonds de page et de visuel | Placement : bandeau, menu, titres (utiliser la page Gabarits) |
| Cartes KPI : arrondi 14, valeur centrée, libellé dessous, sans barre ni ombre | Contenu HTML (couleurs écrites dans le code) |
| Tableaux, matrices, segments, boutons, couleurs des graphiques | Étiquette de comparaison d'un KPI (Format › Étiquette de référence) |

Le thème a été vérifié avec le schéma officiel des thèmes Power BI (version 2.159).

**Couleurs**

| Usage | Couleurs | Source |
|---|---|---|
| Fonds | page `#0F1E33`, menu `#0A1628`, cartes `#162A45` / `#1B3150`, lignes `#2A3F5E` | — |
| Textes | `#D4D4D4`, titres blanc, secondaire `#9D9D9D` | — |
| Accent, sélection | `#6BAED6`, `#2171B5` | Bleus ColorBrewer |
| Niveaux Essentiel, Courant, Avancé | `#21918C`, `#5EC962`, `#FDE725` : plus lumineux = plus avancé | Viridis |
| Séries de graphiques | `#56B4E9`, `#E69F00`, `#009E73`, `#CC79A7`, `#F0E442`, `#D55E00`, `#D4D4D4` | Okabe-Ito, version sombre (sans noir ni bleu foncé) |
| Bon / neutre / mauvais | bleu `#6BAED6` / gris `#9D9D9D` / orange `#E69F00` | Pas d'opposition rouge / vert |

**Accessibilité**
- Tous les textes ont un contraste d'au moins 4,5:1 sur leur fond, le seuil WCAG AA.
- Les bordures et les éléments graphiques atteignent au moins 3:1.
- La couleur n'est jamais seule porteuse d'information : le niveau est écrit sur chaque carte, et une comparaison s'accompagne d'une flèche et d'un signe (▲ +12,4 %).
- **Règle à respecter** : ne jamais écrire de texte en `#21918C`, qui n'atteint que 3,8:1. Cette couleur sert uniquement aux bordures et aux fonds de pastille.
- **Limite** : un thème sombre ne convient pas à tout le monde. Par exemple, certaines personnes astigmates lisent moins bien un texte clair sur fond sombre.

## Présentation

Le fichier `Aide_memoire_DAX_comprendre_le_rapport.pptx` présente le rapport en 10 diapositives : les pages, les sources, le classeur, le thème et la mise en route.

## Dépendances

- Visuel personnalisé **HTML Content Secure** (AppSource, édition certifiée), utilisé pour les formules colorées, les fiches et le Top 25. Sans ce visuel installé, ces zones restent vides.

## Licence

- **Ce rapport, ses fiches, ses mesures, ses données fictives, le classeur `COMMANDES_DAX.xlsx` et le thème D2** sont sous licence **Creative Commons Attribution 4.0 International (CC BY 4.0)**. Vous pouvez les utiliser, les copier, les modifier et les partager, y compris à des fins commerciales, à condition de **citer la source** (par exemple « Aide-mémoire DAX (Power BI), CC BY 4.0 ») et d'indiquer si des modifications ont été faites. Texte de la licence : <https://creativecommons.org/licenses/by/4.0/deed.fr>
- **Exemples marqués 🔧 dans le classeur** : adaptés de Microsoft Learn (CC BY 4.0).
- **Descriptions des fonctions DAX** : elles sont lues sur Microsoft Learn à chaque actualisation et appartiennent à Microsoft. Le dépôt source de cette documentation (MicrosoftDocs/query-docs) est publié sous CC BY 4.0 pour les textes et sous MIT pour le code.
- **Palettes de couleurs** : Okabe-Ito (Okabe et Ito, *Color Universal Design*, 2008), Viridis (van der Walt et Smith, matplotlib) et ColorBrewer (Cynthia Brewer, colorbrewer2.org).
