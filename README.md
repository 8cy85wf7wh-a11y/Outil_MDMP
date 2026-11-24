# Outil de restitution MDMP (US Army)

Page web autonome (`index.html`) qui guide la conduite de la MDMP (Military Decision-Making Process) et produit les restitutions au format américain : briefings, warning orders et OPORD brief.

Interface et restitutions en anglais.

## Sources doctrinales

- CGSOC DTAC DOCMAT, *The Military Decision-Making Process (MDMP) Quick Reference Guide*, v25.2, 27 Aug 25 (FM 5-0, Nov 24, chap. 5 et app. D) : structure, sous-étapes, sorties et formats de briefing.
- Center for Army Lessons Learned, Handbook 23-07, *Military Decision-Making Process: Organizing and Conducting Planning*, Nov 23 : bonnes pratiques par étape, critères de sélection des COA, matrice de décision, méthodes de wargame.

La structure suit le QRG (le plus récent). Les éléments ajoutés depuis le CALL sont marqués « CALL ».

## Fonctions

- **Tableau de bord** (onglet *Dashboard*) : vue en lecture seule des données saisies — bandeau de classification, indicateurs clés, avancement par étape, mission et intention, état des produits avec rubriques manquantes, prochaines actions, chronologie, tâches, CCIR/EEFI, hypothèses, risques, COA et matrice de décision, ordre supérieur chargé.
- **Dépôt de l'ordre de l'échelon supérieur** (OPORD, FRAGORD, WARNORD, annexes A à V), tout format : PDF, Word, Excel, PowerPoint (Open XML), OpenDocument, RTF, HTML, texte, anciens formats Office binaires, photos de pages. Claude extrait les éléments destinés à l'unité désignée (mission, intention et concept du supérieur, tâches explicites, missions sur ordre, contraintes, articulation, chronologie, ennemi, CCIR, coordination, soutien, transmissions), chacun avec sa référence de paragraphe. Revue champ par champ avant application.
- **7 étapes** : sous-étapes du QRG, sorties clés (CALL, tableau 3-1), leçons CALL, formulaires de travail (assistant d'énoncé de mission, fiches COA, critères de sélection, fiche de wargame, matrice de décision pondérée).
- **Restitutions** dans l'ordre doctrinal : Mission Analysis Brief, COA Brief, COA Analysis Brief (optionnel), COA Decision Brief, OPORD Brief, WARNORD 1 à 3. Taux de complétude, éléments manquants affichés « Not yet developed ».
- **Exports** : présentation plein écran, PowerPoint (.pptx), HTML imprimable en PDF, texte.
- **Sauvegarde** : compte Claude (espace personnel ou d'équipe) ; copie locale dans le navigateur en attendant la synchronisation, nouvelle tentative automatique en cas de coupure ; sauvegarde et import JSON (données contrôlées à l'import).
- **Accessibilité** : navigation clavier, lien d'évitement, cibles tactiles de 44 px, présentation plein écran sur téléphone, couleurs de bandeau de classification (UNCLASSIFIED vert, CUI violet, C bleu, S rouge, TS orange, TS/SCI jaune).

## Vérification (v2.4, 24 nov. 2026)

Quatre vérifications indépendantes (doctrine, ergonomie/accessibilité, code/sécurité, fonctionnel) puis tests de non-régression automatisés (Playwright, Chrome ; rendu PPTX sous LibreOffice). Corrections : libellés et contenus doctrinaux (paragraphes OPORD, IPOE, tâches tactiques, règle du tiers), matrice de décision (rangs entiers 1 à n, égalité sans COA préféré), échappement des données importées, synchronisation sans perte en cas de coupure, mise en page mobile et diapositives.

## Utilisation

| Contexte | Sauvegarde | Extraction de l'ordre | Exports fichiers |
|---|---|---|---|
| Artefact Claude (claude.ai) | Compte Claude | Oui (usage Claude de l'utilisateur) | Oui |
| Fichier ouvert dans un navigateur ou hébergé (GitHub Pages…) | Navigateur local | Non | Oui (téléchargement direct) |

Hors de Claude, ouvrir `index.html` dans un navigateur récent. Une connexion internet est nécessaire pour les polices, le module PowerPoint (pptxgenjs 4.0.1), le lecteur PDF (pdf.js 4.10.38) et, sur les navigateurs anciens, le module de décompression (pako 2.1.0), chargés depuis jsDelivr.

## Limites

- L'extraction ne produit ni tâches implicites ni conclusions d'IPOE : elles relèvent de l'analyse d'état-major.
- Les tableaux 4-1, 5-5 et 6-2 du CALL 23-07 ne sont pas repris (non disponibles en texte).
- Anciens formats binaires (.doc, .xls, .ppt, .msg) : seul le texte brut est récupéré, sans mise en forme, avec des fragments parasites possibles. Photos HEIC lues seulement si le navigateur sait les décoder. Au-delà de 40 pages scannées par document, seules les 40 premières sont envoyées.
- Outil d'entraînement, non officiel.
