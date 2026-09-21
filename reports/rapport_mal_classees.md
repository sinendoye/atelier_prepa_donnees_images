## Méthodologie

1. **Candidats automatiques** : les doublons présents dans des classes différentes (Partie 6, empreinte des pixels) sont quasiment toujours des erreurs de tri, car une même image ne peut appartenir qu'à une classe.
2. **Contrôle visuel** : parcours de chaque classe en mosaïques de 40 images par planche.
3. **Décision** : chaque intrus est reclassé si sa vraie classe est certaine, retiré s'il est douteux ou s'il n'est pas un déchet.

## Intrus identifiés

| Fichier | Classe actuelle | Contenu réel | Action | Classe correcte |
|---|---|---|---|---|
| `cardboard161.jpg` | cardboard | Bocal en verre (vue du dessus) | reclasser | glass |
| `cardboard86d.jpg` | cardboard | Bouteille plastique, bouchon vert | reclasser | plastic |
| `glass12er.jpg` | glass | Publicité de magazine | reclasser | paper |
| `metal111.jpg` | metal | Bouteille d'huile d'olive en verre | reclasser | glass |
| `paper201.jpg` | paper | Objet en cuir/métal | reclasser | metal |
| `plastic112.jpg` | plastic | Bouteille avec bord en verre visible | reclasser | glass |
| `image-blanche-512x384 (6).jpg` | metal | Image artificielle (pas un déchet) | retirer | - |
| `image-noire-512x384 (7).png` | metal | Image artificielle (pas un déchet) | retirer | - |
| `image-noire-512x384 (6).png` | glass | Image artificielle (pas un déchet) | retirer | - |
| `image-violet-512x384 (8).gif` | glass | Image artificielle (pas un déchet) | retirer | - |
| `image-blanche-512x384 (5).jpg` | cardboard | Image artificielle (pas un déchet) | retirer | - |
| `image-violet-512x384 (7).gif` | cardboard | Image artificielle (pas un déchet) | retirer | - |
| `metal91 (5).jpg` | metal | Doublon présent dans deux classes (image ambiguë) | retirer | - |
| `plastic152 (5).jpg` | plastic | Doublon présent dans deux classes (image ambiguë) | retirer | - |
| `glass115 (5).jpg` | glass | Doublon présent dans deux classes (image ambiguë) | retirer | - |
| `glass176 (5).jpg` | glass | Doublon présent dans deux classes (image ambiguë) | retirer | - |

## Limites

Le contrôle visuel est subjectif et peut laisser passer un intrus visuellement proche de sa classe. Les cas ambigus sont retirés plutôt que reclassés. Le dossier `raw/` n'est pas modifié : les actions seront appliquées dans `cleaned/` (Partie 9).
