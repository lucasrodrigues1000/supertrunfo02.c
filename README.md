# supertrunfo02.c

#include <stdio.h>
#include <stdlib.h>

#define NUM_CIDADES 2

typedef struct {
    char nome[20];
    int populacao;
} Cidade;

int main() {
    Cidade cidades[NUM_CIDADES] = {
        {"Cidade A", 500000},
        {"Cidade B", 1000000},
       
    };

    int escolha1, escolha2;
    printf("Escolha duas cidades (0 a %d): ", NUM_CIDADES - 1);
    scanf("%d %d", &escolha1, &escolha2);

    if (escolha1 >= 0 && escolha1 < NUM_CIDADES && escolha2 >= 0 && escolha2 < NUM_CIDADES) {
        printf("%s (População: %d) vs %s (População: %d)\n", 
               cidades[escolha1].nome, cidades[escolha1].populacao, 
               cidades[escolha2].nome, cidades[escolha2].populacao);
        
        if (cidades[escolha1].populacao > cidades[escolha2].populacao) {
            printf("%s vence!\n", cidades[escolha1].nome);
        } else if (cidades[escolha1].populacao < cidades[escolha2].populacao) {
            printf("%s vence!\n", cidades[escolha2].nome);
        } else {
            printf("Empate!\n");
        }
    } else {
        printf("Escolha inválida!\n");
    }

    return 0;
}
