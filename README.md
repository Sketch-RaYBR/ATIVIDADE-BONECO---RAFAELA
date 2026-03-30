**-----ATIVIDADE 01-----**


package javaapplication1;

public class JavaApplication1 {

    public static void main(String[] args) {
    
    System.out.println(" +\"\"\"\"\"+");
    System.out.println("[| o o |]");
    System.out.println(" |  ^  | ");
    System.out.println(" | '-' | ");    
    System.out.println(" +-----+");
    }        
}


**-----ATIVADADE 02-----**


package javaapplication1;

public class JavaApplication1 {

    public static void main(String[] args) {
        // Dados de entrada
        double lat1 = 25.0;
        double lon1 = 35.0;
        double lat2 = 35.5;
        double lon2 = 25.5;

        // Raio da Terra em km
        double raio = 6371.01;

        // Converter graus para radianos
        lat1 = Math.toRadians(lat1);
        lon1 = Math.toRadians(lon1);
        lat2 = Math.toRadians(lat2);
        lon2 = Math.toRadians(lon2);

        // Fórmula da distância
        double distancia = raio * Math.acos(
                Math.sin(lat1) * Math.sin(lat2) +
                Math.cos(lat1) * Math.cos(lat2) *
                Math.cos(lon1 - lon2)
        );

        // Saída
        System.out.println("A distância entre esses pontos é: " + distancia + " km");
    }
}


**-----ATIVIDADE 03-----**


package javaapplication1;

import java.util.Scanner;

public class JavaApplication1 {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Digite uma algo que venha a mente: ");
        String texto = scanner.nextLine();

        int letras = 0;
        int numeros = 0;
        int espacos = 0;
        int outros = 0;

        for (int i = 0; i < texto.length(); i++) {
            char c = texto.charAt(i);

            if (Character.isLetter(c)) {
                letras++;
            } else if (Character.isDigit(c)) {
                numeros++;
            } else if (Character.isWhitespace(c)) {
                espacos++;
            } else {
                outros++;
            }
        }

        System.out.println("Letras: " + letras);
        System.out.println("Números: " + numeros);
        System.out.println("Espaços: " + espacos);
        System.out.println("Outros caracteres: " + outros);
    }
}


**-----ATIVIDADE 04-----**


package javaapplication1;

import java.util.Scanner;
    
    public class JavaApplication1 {
    
        public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int tentativa = 0;
        boolean acertou = false;
        char resposta;

        do {
            tentativa++;

            System.out.println("\nQuestão (Matemática):");
            System.out.println("Qual é o valor de π (pi) aproximadamente?");
            System.out.println("(a) 2,14");
            System.out.println("(b) 3,14");
            System.out.println("(c) 4,13");
            System.out.println("(d) 3,41");
            System.out.println("(e) 5,14");
            System.out.print("Escolha uma alternativa: ");

            resposta = scanner.next().toLowerCase().charAt(0);

            switch (resposta) {
                case 'b':
                    System.out.println("Resposta correta!");
                    System.out.println("Você acertou na tentativa " + tentativa);
                    acertou = true;
                    break;

                case 'a':
                case 'c':
                case 'd':
                case 'e':
                    System.out.println("Resposta incorreta.");
                    break;

                default:
                    System.out.println("Opção inválida.");
                    tentativa--; // não conta tentativa inválida
            }

        } while (!acertou && tentativa < 3);

        if (!acertou && tentativa == 3) {
            System.out.println("\nResposta incorreta nas 3 tentativas.");
        }
    }
}
