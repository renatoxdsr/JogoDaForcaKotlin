import java.util.*
import kotlin.reflect.typeOf

fun main() {

    val desafio1: Desafio = Desafio("Paraiso", "Uma novela da Globo");
    var letra: String;
    var delimitar = "";
    var palavraSplit = desafio1.palavra.split(delimitar).slice(1..contarLetras(desafio1.palavra));
    var diferentes = linkedSetOf<String>();
    var corretas = linkedSetOf<String>();
    var erradas = linkedSetOf<String>();
    var palavraadescobrir = arrayListOf<String>();
    var tentativa: Int = 0;
    var numTentativas = ((desafio1.palavra.length) / 2) + 1;
    var i = 0;

    for (letra in palavraSplit) {
        if (letra in palavraSplit[i]) {
            diferentes.add(letra)
            i++
        }
    }
    for(letra in palavraSplit) {
        palavraadescobrir.add("_")
    }

    println("Bem-vindo ao Jogo da Forca. Aqui para ganhar você tem que advinhar a palavra.\n" +
            "A DICA é o seguinte --> ${desafio1.dica}\n")

    println("Vou te ajudar: a palavra tem  ${contarLetras(desafio1.palavra)} letras, das quais ${diferentes.size} delas são diferentes.")
    println("Agora você tem um total de ${numTentativas} tentativas no jogo.")

    while (tentativa < numTentativas || palavraSplit != palavraadescobrir) {
        println("Essa é a sua ${tentativa+1}º tentativa nesta jogada atual, você poderá ter mais ${ numTentativas - tentativa} chance(s)")
        println("Digite uma letra ou FIM se desejar terminar o jogo. ")
        println("Seu jogo atual está: ${palavraadescobrir}")
        letra = readLine().toString().uppercase(Locale.getDefault())

        val x = 0

        for(i in 0..palavraSplit.size - 1) {
            if(letra== palavraSplit[1]){
                x++
                palavraadescobrir[i] = letra
            }
        }
        if (letra in diferentes) {
            println("YEH!!!Você acertou a letra ${letra}, vamos lá")
            corretas.add(letra)
            tentativa++
        }
        else {
            println("A letra ${letra} não contém na palavra que deseja advinhar")
            erradas.add(letra)
            tentativa++
        }
        println("ACERTOS: ${corretas}")
        println("ERROS: ${erradas}")
    }
    if(erradas.size === numTentativas){
        print("Você perdeu!")
    } else if (palavraSplit.equals(palavraadescobrir)){
        println("Parabéns, Você acertou toda a palavra!")
    }else null



}
class Desafio(
    val palavra: String,
    val dica: String
)

fun contarLetras(palavra: String): Int {
    return palavra.length
}
