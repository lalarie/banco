# banco
#include <stdio.h>

int main() {
    float saldo = 1000.00;
    int opcao;
    float valor;

    do {
        printf("Menu principal do banco da Larissa:\n");
        printf("1- Consulta ao saldo\n");
        printf("2- Depositar algum valor\n");
        printf("3- Retirar algum valor\n");
        printf("4- Sair\n");
        printf("Escolha uma opção (de 1 a 4): ");
        scanf("%d", &opcao);

        switch(opcao) {
            case 1:
                printf("Saldo atual: R$ %.2f\n", saldo);
                break;

            case 2:
                printf("Digite o valor a ser depositado: R$ ");
                scanf("%f", &valor);
                if (valor > 0) {
                    saldo += valor;
                    printf("Depósito realizado com sucesso.\n");
                } else {
                    printf("Valor inválido para depósito.\n");
                }
                printf("Saldo atualizado: R$ %.2f\n", saldo);
                break;

            case 3:
                printf("Digite o valor a ser retirado: R$ ");
                scanf("%f", &valor);
                if (valor > 0) {
                    if (valor <= saldo) {
                        saldo -= valor;
                        printf("Retirada realizada com sucesso.\n");
                    } else {
                        printf("Saldo insuficiente!\n");
                    }
                } else {
                    printf("Valor inválido para retirada.\n");
                }
                printf("Saldo atualizado: R$ %.2f\n", saldo);
                break;

            case 4:
                printf("fim\n");
                break;

            default:
                printf("Opção inválida!!! Por favor, escolher uma opção entre 1 até 4.\n");
                break;
        }
    } while (opcao != 4); // O laço continua até que a opção seja 4

    return 0; // Retorna 0 para indicar que o programa terminou corretamente
}
