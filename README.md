#include <stdio.h>
#include <stdlib.h> 


char nomeg[50];

void invalido(){
    printf("Opçcao Invalida.\n");
    while (getchar() != '\n');
}

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
    
    do {
      scanf(" %c", &escolha);
      switch(escolha){
        case 'a':
            printf("Você decide pagar o imposto e é permitido entrar na cidade.\n");
            break;
        case'b':
            printf("Você tenta passar sem pagar, mas é pego pelos guardas e precisa pagar uma multa.\n");
            printf("Após pagar a multa, você finalmente é permitido entrar na cidade.\n");
             break;
        case 'c':
             printf("Os guardas ficam com medo e te deixam passar.\n");
             break;
        default:
           invalido();
           break;
        }
    
    }while(escolha != 'a' && escolha != 'b' && escolha != 'c');
    continuartela();
    printf("Com isso voce finalmente consegue entrar dentro da cidade,oque voce ira fazer?\n");
    printf("a) Andar reto sem destino\n");
    printf("b) Peguntar sobre a guilda para alguem\n");
    scanf(" %c",&escolha);

    if (escolha == 'a')
    {
        printf("Como a cidade e pequena voce acaba encontrando a guilda\n");
    }
    else if(escolha == 'b'){
        printf("Voce pergunta a um homem que nitidamente parece um guerreiro\n");
        printf("%s: Ola amigo,por algum acaso voce sabe onde fica a guilda?\n",nomeg);
        printf("Estranho:Guilda? Obvio meu amigo(a),e so continuar reto que voce chegara la\n");
    }
    else{
        printf("Opção invalida.\n");
    }
    continuartela();
    printf("E finalmente depois de uma curta caminhada voce encontra a guilda e entra nela\n");
    printf("Dentro da guilda o que voce ira fazer?\n");
    printf("a)Falar com a atendente\n");
    printf("b)Procurar em volta\n");
    scanf("%c",&escolha);
    if (escolha == 'a')
    {
        printf("Atendente: Perfeito irei te mostrar sobre a missao\n");
    }
    else if (escolha == 'b')
    {
        printf("Voce nao encontra nada de interessante e acaba voltando pra conversar com a atendente\n");
        printf("Atendente: Perfeito irei te mostrar sobre a missao\n");
    }
    else{
        printf("Opçcao invalida.\n");
    }
   
   return 0;
}
