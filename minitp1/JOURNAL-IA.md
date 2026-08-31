# Journal IA — Mini-TP 1 — ANDRIAKOTOHARISON Irina

- Fonction soumise : ``` fun totalParProduit(liste: List<Collecte>): Map<String, Double> =
  liste.groupBy { it.produit.nom }.mapValues { it.value.sumOf { it.poidsKg } } ```

- Remarque principale de l'IA :
  - Sensibilité à la casse (Bug potentiel) : Utiliser it.produit.nom risque d'isoler des doublons si les noms diffèrent par la casse.
  - Lisibilité du it imbriqué : Le second it à l'intérieur de sumOf { it.poidsKg } masque le it de mapValues. C'est syntaxiquement correct, mais cela force une ré-lecture pour comprendre que le premier concerne l'entrée de la Map (Map.Entry) et le second l'élément Collecte.
  - Clarté de l'intention : Remplacer it.value par de la destructuration (_, collectes) rendrait l'intention immédiatement explicite tout en évitant le masquage de it : ```.mapValues { (_, collectes) -> collectes.sumOf { it.poidsKg } }.```
  - Style Kotlin (Idiomatique) : L'enchaînement des fonctions d'extension (groupBy + mapValues) et la syntaxe à expression unique (=) sont parfaitement idiomatiques en Kotlin pour ce type de transformation.
- Mon verdict (accepte / rejette / nuance) et pourquoi : J'accepte car les remarques sont très pertinentes. Surtout celle sur la sensibilité à la casse car c'est un détail que souvent je peux oublier. Et concernant les autres critiques je dois avouer que c'est complètement nouveau pour moi, je tacherai de m'en souvenir.
