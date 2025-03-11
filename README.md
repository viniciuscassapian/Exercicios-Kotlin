# Exercicios-Kotlin
#Desafio Sequencias basicas ( cigarro)
fun main() {
    println("Quantos cigarros você fuma por dia?")
    val cigarrosPorDia = readLine()!!.toInt()
    println("Quantos anos você já fumou?")
    val anosFumando = readLine()!!.toInt()
    val diasPerdidos = (cigarrosPorDia * 10 * anosFumando * 365) / 1440
    println("Você perdeu aproximadamente $diasPerdidos dias de vida.")
}

#Desafio 3 segmentos de reta
fun main() {
    println("Digite o comprimento do primeiro segmento de reta:")
    val a = readLine()!!.toDouble()

    println("Digite o comprimento do segundo segmento de reta:")
    val b = readLine()!!.toDouble()

    println("Digite o comprimento do terceiro segmento de reta:")
    val c = readLine()!!.toDouble()

    if (a + b > c && a + c > b && b + c > a) {
        println("É possível formar um triângulo.")
    } else {
        println("Não é possível formar um triângulo.")
    }
}

#Desfio de forma triângulos
fun main() {
    println("Digite o comprimento do primeiro segmento de reta:")
    val a = readLine()!!.toDouble()

    println("Digite o comprimento do segundo segmento de reta:")
    val b = readLine()!!.toDouble()

    println("Digite o comprimento do terceiro segmento de reta:")
    val c = readLine()!!.toDouble()

    if (a + b > c && a + c > b && b + c > a) {
        when {
            a == b && b == c -> println("É um triângulo Equilátero.")
            a == b || a == c || b == c -> println("É um triângulo Isósceles.")
            else -> println("É um triângulo Escaleno.")
        }
    } else {
        println("Não é possível formar um triângulo.")
    }
}

#Desafio Jokenpo
import kotlin.random.Random

fun main() {
    val opcoes = listOf("Pedra", "Papel", "Tesoura")
    println("Bem-vindo ao jogo JoKenPo!")
    println("Escolha uma opção: Pedra, Papel ou Tesoura")
    var escolhaJogador = readLine()?.capitalize()
    while (escolhaJogador !in opcoes) {
        println("Escolha inválida! Escolha novamente: Pedra, Papel ou Tesoura")
        escolhaJogador = readLine()?.capitalize()
    }
    val escolhaComputador = opcoes[Random.nextInt(0, 3)]
    println("Você escolheu: $escolhaJogador")
    println("O computador escolheu: $escolhaComputador")
    when {
        escolhaJogador == escolhaComputador -> println("Empate!")
        (escolhaJogador == "Pedra" && escolhaComputador == "Tesoura") ||
        (escolhaJogador == "Papel" && escolhaComputador == "Pedra") ||
        (escolhaJogador == "Tesoura" && escolhaComputador == "Papel") -> println("Você ganhou!")
        else -> println("Você perdeu!")
    }
}
#Desafio Jogo de adivinhação
import kotlin.random.Random

fun main() {
    val numeroSorteado = Random.nextInt(1, 6)
    println("Tente adivinhar o número sorteado entre 1 e 5!")
    print("Digite seu palpite: ")
    val palpite = readLine()?.toIntOrNull()
    if (palpite == null || palpite !in 1..5) {
        println("Por favor, insira um número entre 1 e 5.")
    } else {
        if (palpite == numeroSorteado) {
            println("Parabéns! Você acertou o número!")
        } else {
            println("Que pena! O número sorteado era $numeroSorteado. Tente novamente!")
        }
    }
}
