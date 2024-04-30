#include <stdio.h>
#include <stdlib.h> 


char nomeg[50];

void limparTela() {
    #ifdef _WIN32
        system("cls");
    #else
        system("clear");
    #endif
}

void continuartela() {
    printf("Pressione qualquer tecla para continuar\n");
    char tecla;
    scanf(" %c", &tecla); 
    if (tecla) { 
        limparTela();
    }
}



void InicioJogo() {
    char nomejogador[50];
    printf("Ola jogador, qual seu nome?\n");
    scanf("%s", nomejogador); 
    printf("E qual sera o nome do seu guerreiro(a)?\n");
    scanf("%s", nomeg); 
    printf("Bem vindo(a) %s, nessa história você irá seguir o caminho do(a) guerreiro(a) %s\n", nomejogador, nomeg); 
    continuartela();
} 

int main() {
    InicioJogo();

    printf("Você é o(a) %s que está a caminho da cidade em busca da guilda, uma casa onde pode conseguir missões.\n", nomeg);
    printf("Chegando perto do portão, dois guardas te impedem de entrar e falam:\n");
    printf("Pare aí! ");
    printf("Antes de entrar na cidade, você precisa pagar o imposto de visitante.\n");

    printf("O que você ira fazer?\n");
    printf("a) Pagar o imposto\n");
    printf("b) Tentar passar sem pagar\n");
    printf("c) Falar que isso é um abuso e mentira\n");

    char escolha;
    scanf(" %c", &escolha); 
    limparTela();

    if(escolha == 'a') {
        printf("Você decide pagar o imposto e é permitido entrar na cidade.\n");
    }
    else if(escolha == 'b') {
        printf("Você tenta passar sem pagar, mas é pego pelos guardas e precisa pagar uma multa.\n");
        printf("Após pagar a multa, você finalmente é permitido entrar na cidade.\n");
    }
    else if(escolha == 'c') {
        printf("Os guardas ficam com medo e te deixam passar.\n");
    }
    else {
        printf("Opção inválida.\n");
    }

    return 0;
}
