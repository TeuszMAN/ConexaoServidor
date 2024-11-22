import java.io.*;
import java.net.*;

public class ServidorTCP {
    public static void main(String[] args) {
        try {
            // Cria o ServerSocket que escuta na porta 12345
            ServerSocket serverSocket = new ServerSocket(12345);
            System.out.println("Servidor aguardando conexão...");

            // Aceita uma conexão de um cliente
            Socket clientSocket = serverSocket.accept();
            System.out.println("Conexão estabelecida com o cliente " + clientSocket.getInetAddress());

            // Fluxos de entrada e saída para comunicação
            PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);
            BufferedReader in = new BufferedReader(new InputStreamReader(clientSocket.getInputStream()));

            // Envia uma mensagem de boas-vindas ao cliente
            out.println("Bem-vindo ao servidor! Envie um conjunto de números.");

            // Recebe o conjunto de números do cliente
            String numerosRecebidos = in.readLine();
            System.out.println("Números recebidos do cliente: " + numerosRecebidos);

            // Processa os números recebidos (exemplo de soma dos números)
            String[] numerosArray = numerosRecebidos.split(",");
            int soma = 0;
            for(int i = 0; i < numerosArray.length; i++){
                for (String numero : numerosArray) {
                    soma += Integer.parseInt(numero.trim());
                }
                System.out.println("Soma dos números recebidos: " + soma);
            }


            // Fecha o cliente e o servidor
            in.close();
            out.close();
            clientSocket.close();
            serverSocket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
