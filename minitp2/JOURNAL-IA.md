# JOURNAL-IA - Mini Tp 2 - ANDRIAKOTOHARISON Irina

- Écart choisi (programme et nature de l'écart) : 
```
fun main() = runBlocking {
val duree = measureTimeMillis {
    val poidsVanille = async {
    delay(1000)
    4.5
    }
    val poidsCafe = async {
    delay(800)
    6.0
    }
println("Poids total : " + (poidsVanille.await() + poidsCafe.await()) + " kg")
}
println("Durée totale : environ $duree ms")
}
```
- Explication reformulée avec mes mots (3 lignes max) :
  Les async sont deja démarrés dès que
  le compilateur passe sur les declarations en haut.
  Lors du premier await() dans println()
  il exécute uniquement le delay de 1000ms puis
  recupere les valeurs (avec celuide poidsCafe
  qui est deja ecoule avec les 1000ms)

