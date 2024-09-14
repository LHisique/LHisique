🚀 Sobre mim
Eu sou uma pessoa desenvolvedora full-stack... estudo programação faz 50 anos. sou alérgico à java e só trabalho com C#

Referência
Awesome Readme Templates
Awesome README
How to write a Good readme
Stack utilizada
Front-end: React, Redux, TailwindCSS

Back-end: Node, Express, visual estudio

Instalação
Instale my-project com npm

  using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Passo 1: Criar listas para armazenar os nomes e os preços dos produtos
        List<string> nomesProdutos = new List<string>();
        List<decimal> precosProdutos = new List<decimal>();

        // Passo 2: Cadastro de 5 produtos
        for (int i = 0; i < 5; i++)
        {
            Console.Write("Digite o nome do produto {0}: ", i + 1);
            string nomeProduto = Console.ReadLine();
            nomesProdutos.Add(nomeProduto);

            Console.Write("Digite o preço do produto {0}: ", i + 1);
            decimal precoProduto = Convert.ToDecimal(Console.ReadLine());
            precosProdutos.Add(precoProduto);
        }

        // Variáveis para armazenar o cupom fiscal e o total da compra
        string cupomFiscal = "\n--- Cupom Fiscal ---\n";
        decimal totalCompra = 0;
        decimal desconto = 0.10m; // Desconto fixo de 10%

        // Passo 3: Loop de compra
        while (true)
        {
            // Solicita o nome do produto que deseja comprar
            Console.Write("\nDigite o nome do produto que deseja comprar (ou 'sair' para finalizar): ");
            string nomeCompra = Console.ReadLine();

            // Se o usuário digitar "sair", encerra o loop
            if (nomeCompra.ToLower() == "sair")
            {
                break;
            }

            // Verifica se o produto existe na lista
            int indiceProduto = nomesProdutos.IndexOf(nomeCompra);
            if (indiceProduto == -1)
            {
                Console.WriteLine("Produto não encontrado!");
                continue; // Pula para a próxima iteração do loop
            }

            // Solicita a quantidade desejada do produto
            Console.Write("Digite a quantidade que deseja comprar: ");
            int quantidade = Convert.ToInt32(Console.ReadLine());

            // Passo 4: Calcula o preço total do item com desconto
            decimal precoUnitario = precosProdutos[indiceProduto];
            decimal precoTotalItem = precoUnitario * quantidade;
            decimal valorDesconto = precoTotalItem * desconto;
            decimal precoComDesconto = precoTotalItem - valorDesconto;

            // Adiciona informações do item ao cupom fiscal
            cupomFiscal += string.Format("{0} x {1} @ {2:C} = {3:C} (Desconto: {4:C})\n",
                quantidade, nomeCompra, precoUnitario, precoComDesconto, valorDesconto);

            // Adiciona o preço total com desconto ao total da compra
            totalCompra += precoComDesconto;
        }

        // Passo 5: Exibe o cupom fiscal
        cupomFiscal += "\nTotal da compra: " + totalCompra.ToString("C");
        Console.WriteLine(cupomFiscal);
        Console.ReadKey();

    }
}
Funcionalidades
Um mercado básico de compras de produtos
ao escolher seus produtos, basta escoher a quantidade e comprar
Emite uma nota fiscal dos produtos e a quantidade
Todos os valores tem um desconto de 10%
