---
name: ab-test
description: Analyser les résultats d'un test A/B comme un senior product manager. À utiliser quand l'utilisateur partage des métriques d'expérience, des captures d'écran ou un résumé de résultats et veut des enseignements, des points de vigilance, une lecture par segment, une estimation de l'impact business, ou une recommandation de déploiement, de retour arrière ou de nouveau test.
---

# Analyse de test A/B

Transformer des résultats d'expérimentation en décision produit, pas seulement en tableau de scores.

## Workflow

1. Cadrer l'expérience : identifier les variantes comparées, l'hypothèse, la métrique principale, les métriques secondaires, les métriques de protection, le ciblage, la répartition, la taille d'échantillon, la durée, et les points de vigilance évidents.
2. Vérifier l'intégrité des résultats avant de les interpréter : signaler les risques comme un échantillon trop faible, une durée trop courte, un déséquilibre de répartition (sample ratio mismatch), un tracking ambigu, des problèmes d'exposition, ou un changement de variante pour un même utilisateur.
3. Dire quelle variante performe le mieux sur la métrique principale, ce qui se passe sur les métriques secondaires, et si le résultat est significatif, mixte ou inconclusif.
4. Chercher les effets hétérogènes : déterminer si la variante test affecte différemment certains segments d'utilisateurs, et nommer les segments à regarder quand c'est pertinent.
5. Lister les calculs business utiles quand les données le permettent, par exemple l'impact annuel sur le revenu, les réservations incrémentales, l'impact par utilisateur exposé, l'opportunité par segment, ou le coût potentiel d'un mauvais choix.
6. Lister les questions précises auxquelles l'analyse doit répondre, surtout quand l'utilisateur a besoin de structurer le compte-rendu et pas seulement d'interpréter un résultat final.
7. Traduire les résultats en enseignement produit ou comportemental plutôt que de répéter les chiffres.
8. Recommander une seule suite : déploiement, retour arrière, ou nouveau test.
9. Anticiper la suite selon le résultat :
   - Positif et significatif : préciser s'il faut un déploiement progressif, quels groupes d'utilisateurs inclure en premier, quelles métriques de protection surveiller, et si un nettoyage technique comme la suppression du feature flag doit être prévu.
   - Négatif et significatif : expliciter ce qui a quand même bien fonctionné, les apprentissages, ce qui aurait pu être fait différemment, et ce qu'il faut ajuster avant un nouveau test.
   - Non significatif : décider s'il faut prolonger, retester, ou arrêter ; expliciter les contraintes de temps et de ressources, ce qui peut être changé, ce qui doit rester stable, et comment capitaliser sur les apprentissages si aucun nouveau test n'est lancé.
10. Proposer 1 à 3 itérations concrètes, chacune reliée à une hypothèse.

## Sortie attendue

Utiliser cette structure sauf si l'utilisateur demande un autre format.

### Résumé

- Écrire 2 à 4 bullets avec les enseignements principaux.
- Mettre en avant la variante gagnante, ou l'absence de gagnant clair.
- Mentionner les points de vigilance visibles comme une faible taille d'échantillon, une durée courte, un déséquilibre de segment, un déséquilibre de répartition, ou un risque de tracking.

### Questions auxquelles répondre

- Lister 3 à 6 questions précises auxquelles l'analyse doit répondre.
- Privilégier des questions orientées décision, par exemple :
  - Quelle variante faut-il déployer, s'il y en a une ?
  - Certains segments réagissent-ils différemment au point de changer la recommandation ou l'ordre du déploiement ?
  - Le lift observé est-il assez important pour compter au niveau business ?
  - Une métrique de protection se dégrade-t-elle suffisamment pour bloquer le déploiement ?
  - Si le résultat est inconclusif, un nouveau test vaut-il vraiment l'investissement ?

### Lecture par segments

- Lister les coupes utilisateurs pertinentes à inspecter quand c'est utile.
- Prioriser les segments qui peuvent changer la décision plutôt que faire une analyse exhaustive.
- Dire explicitement si une lecture segmentée peut modifier le plan de déploiement, de retour arrière ou de nouveau test.

### Calculs business

- Lister les calculs rapides qu'il serait utile de faire.
- Quantifier seulement si les données d'entrée sont disponibles.
- Si les données d'entrée manquent, dire précisément lesquelles sont nécessaires.

### Enseignements exploitables

- Écrire 3 à 5 bullets qui traduisent le résultat en enseignement comportemental ou produit.
- Relier si possible le résultat à une implication plus large pour le produit ou le business.

### Recommandation

- Dire déploiement, retour arrière, ou nouveau test en 1 à 2 phrases.
- Expliquer pourquoi c'est la meilleure suite.
- Si un déploiement est recommandé, ajouter les métriques de protection à suivre.
- Adapter explicitement la recommandation à l'un des trois cas : positif significatif, négatif significatif, ou non significatif.

### Itérations suivantes

1. Suggérer 2 à 3 expérimentations ou ajustements produit.
2. Ajouter pour chacune une hypothèse courte et l'impact attendu.

## Style

- Être concis et orienté décision.
- Éviter la fausse précision.
- Expliciter les hypothèses et les données d'entrée manquantes.
- Préférer une segmentation utile à la décision plutôt qu'une analyse exhaustive.
- Si le résultat n'est pas significatif, ne pas forcer un gagnant.
