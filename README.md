# dojo-java-exercises
repositorio do curso DevDojo java Virado no Jiraiya

    import java.util.Scanner;

    public class exercio01 {
     public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

        System.out.println("Digite o nome da moeda: ");
        String moeda = scanner.nextLine().toLowerCase();

        double conversao = 0;
        switch (moeda) {
            case "dolar" -> conversao = 5.38;
            case "euro" -> conversao = 5.23;
            case "iene" -> conversao = 0.039;
            case "libra" -> conversao = 6.16;
            default -> {
                System.out.println("Moeda não reconhecida, sera considerado real.");
                System.exit(0);
            }
        }

        System.out.println("Digite o valor anual: ");
        double salarioAnual = scanner.nextDouble();

      double salarioReaisMensalBruto = salarioAnual * conversao;
      //double ConversaoDolar = 5.38;//
      double alicota;
      int mes = 12;
      double salarioReaisMensal = salarioReaisMensalBruto / mes;
     // double salarioReaisMensalBruto = salarioDolarlMensal * ConversaoDolar;*/
    

        if (salarioReaisMensal >= 4664.68) {   
            alicota = 0.275;
        } else if (salarioReaisMensal >= 3751.06) { 
            alicota = 0.225;   
        } else if (salarioReaisMensal >= 2826.66 ) {  
            alicota = 0.15; 
        } else if (salarioReaisMensal >= 1903.99) {
            alicota = 0.075; 
        } else  {
            alicota = 0; 
        }

         double salarioLiquido = salarioReaisMensal - (salarioReaisMensal * alicota);

            System.out.println("(Moeda utilizada: " + moeda + ")");
            System.out.println("Cotação do dia: " + conversao);
            System.out.println("Salario mensal bruto em reais: " + String.format("%.2f" , salarioReaisMensal));
            System.out.println("Salario mensal liquido em reais: " + String.format("%.2f", salarioLiquido));
            System.out.println("Aliquota aplicada: " + (alicota * 100) + "%");
            
        scanner.close();
    }
