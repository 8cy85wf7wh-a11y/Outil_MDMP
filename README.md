# Outil de restitution MDMP (US Army)

Page web autonome (`index.html`) qui guide la conduite de la MDMP (Military Decision-Making Process) et produit les restitutions au format américain : briefings, warning orders et OPORD brief.

Interface et restitutions en anglais.

## Sources doctrinales

- CGSOC DTAC DOCMAT, *The Military Decision-Making Process (MDMP) Quick Reference Guide*, v25.2, 27 Aug 25 (FM 5-0, Nov 24, chap. 5 et app. D) : structure, sous-étapes, sorties et formats de briefing.
- Center for Army Lessons Learned, Handbook 23-07, *Military Decision-Making Process: Organizing and Conducting Planning*, Nov 23 : bonnes pratiques par étape, critères de sélection des COA, matrice de décision, méthodes de wargame.

La structure suit le QRG (le plus récent). Les éléments ajoutés depuis le CALL sont marqués « CALL ».

## Fonctions

- **Dépôt de l'ordre de l'échelon supérieur** (OPORD, FRAGORD, WARNORD, annexes A à V) : PDF, Word .docx, texte ou photos de pages. Claude extrait les éléments destinés à l'unité désignée (mission, intention et concept du supérieur, tâches explicites, missions sur ordre, contraintes, articulation, chronologie, ennemi, CCIR, coordination, soutien, transmissions), chacun avec sa référence de paragraphe. Revue champ par champ avant application.
- **7 étapes** : sous-étapes du QRG, sorties clés (CALL, tableau 3-1), leçons CALL, formulaires de travail (assistant d'énoncé de mission, fiches COA, critères de sélection, fiche de wargame, matrice de décision pondérée).
- **Restitutions** dans l'ordre doctrinal : Mission Analysis Brief, COA Brief, COA Analysis Brief (optionnel), COA Decision Brief, OPORD Brief, WARNORD 1 à 3. Taux de complétude, éléments manquants affichés « Not yet developed ».
- **Exports** : présentation plein écran, PowerPoint (.pptx), HTML imprimable en PDF, texte.
- **Sauvegarde** : compte Claude (espace personnel ou d'équipe) ; sauvegarde et import JSON.

## Utilisation

| Contexte | Sauvegarde | Extraction de l'ordre | Exports fichiers |
|---|---|---|---|
| Artefact Claude (claude.ai) | Compte Claude | Oui (usage Claude de l'utilisateur) | Oui |
| Fichier ouvert dans un navigateur ou hébergé (GitHub Pages…) | Navigateur local | Non | Oui (téléchargement direct) |

Hors de Claude, ouvrir `index.html` dans un navigateur récent. Une connexion internet est nécessaire pour les polices, le module PowerPoint (pptxgenjs 4.0.1) et le lecteur PDF (pdf.js 4.10.38), chargés depuis jsDelivr.

## Limites

- L'extraction ne produit ni tâches implicites ni conclusions d'IPOE : elles relèvent de l'analyse d'état-major.
- Les tableaux 4-1, 5-5 et 6-2 du CALL 23-07 ne sont pas repris (non disponibles en texte).
- Formats non lus : .doc, .pptx, .odt, .rtf (convertir en PDF ou .docx). Au-delà de 40 pages scannées par document, seules les 40 premières sont envoyées.
- Outil d'entraînement, non officiel.
