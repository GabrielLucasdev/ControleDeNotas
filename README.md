import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Informe o número de alunos na turma: ");
        int aluno = scanner.nextInt();

        System.out.print("Informe o número de provas no semestre: ");
        int provas = scanner.nextInt();

        double[][] notas = new double[aluno][provas];

        System.out.println("----------------------------------------");

        for (int i = 0; i < aluno; i++) {
            System.out.println("Informe as notas do aluno " + (i + 1) + ": ");

            for (int a = 0; a < provas; a++) {

                double nota;
                do {
                    System.out.print("Nota " + (a + 1) + ": ");
                    nota = scanner.nextDouble();
                    if (nota < 0) {
                        System.out.println("Nota inválida, insira uma nota maior que 0");
                    }
                } while (nota < 0);
                notas[i][a] = nota;
            }
        }

        int aprovados = 0;
        int reprovados = 0;
        for (int i = 0; i < aluno; i++) {
            double somaDasNotas = 0;
            for (int j = 0; j < provas; j++) {
                somaDasNotas += notas[i][j];
            }

            System.out.println("----------------------------------------");
            System.out.println("Nota final do aluno " + (i + 1) + ": " + somaDasNotas);

            if (somaDasNotas >= 70) {
                System.out.println("Aluno " + (i + 1) + " aprovado");
                System.out.println("----------------------------------------");
                aprovados++;
            } else {
                System.out.println("Aluno " + (i + 1) +" reprovado");
                System.out.println("----------------------------------------");
                reprovados++;
            }
        }

        System.out.println("----------------------------------------");

        System.out.println("Total de alunos aprovados: " + aprovados);
        System.out.println("Total de alunos reprovados: " + reprovados);

        System.out.println("----------------------------------------");
    }
}
