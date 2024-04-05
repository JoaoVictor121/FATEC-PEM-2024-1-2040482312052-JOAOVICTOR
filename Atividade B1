//NOMES DOS INTEGRANTES: Diogo Navarrete, João Victor, Murilo Gonçalvez
//Data: 23/03/2024
//Projeto de PEM Ads Vespertino

#include <stdio.h>

#define TAMANHO_TABULEIRO 8

typedef enum {BRANCO, PRETO} Cor;
typedef enum {PEAO, TORRE, CAVALO, BISPO, RAINHA, REI} TipoPeca;

typedef struct {
    Cor cor;
    TipoPeca tipo;
    int numero;
} Peca;

void inicializarTabuleiro(Peca tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO]);
void exibirTabuleiro(Peca tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO]);

int main() {
    Peca tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO];
    inicializarTabuleiro(tabuleiro);
    exibirTabuleiro(tabuleiro);
    return 0;
}

void inicializarTabuleiro(Peca tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO]) {
    int i, j;
    Cor cor_casa = PRETO;

    for (i = 0; i < TAMANHO_TABULEIRO; i++) {
        for (j = 0; j < TAMANHO_TABULEIRO; j++) {
            // Definir a cor da casa
            if ((i + j) % 2 == 0) {
                cor_casa = PRETO;
            } else {
                cor_casa = BRANCO;
            }

            // Posicionar peças nas primeiras e últimas fileiras
            if (i == 0 || i == TAMANHO_TABULEIRO - 1) {
                if (j == 0 || j == TAMANHO_TABULEIRO - 1) {
                    // Torres
                    tabuleiro[i][j].tipo = TORRE;
                } else if (j == 1 || j == TAMANHO_TABULEIRO - 2) {
                    // Cavalos
                    tabuleiro[i][j].tipo = CAVALO;
                } else if (j == 2 || j == TAMANHO_TABULEIRO - 3) {
                    // Bispos
                    tabuleiro[i][j].tipo = BISPO;
                } else if (j == 3) {
                    // Rainhas
                    tabuleiro[i][j].tipo = RAINHA;
                } else if (j == 4) {
                    // Reis
                    tabuleiro[i][j].tipo = REI;
                }
            } else if (i == 1 || i == TAMANHO_TABULEIRO - 2) {
                // Peões
                tabuleiro[i][j].tipo = PEAO;
            } else {
                // Casas vazias
                tabuleiro[i][j].tipo = -1;
            }

            // Definir a cor da peça
            if (tabuleiro[i][j].tipo != -1) {
                tabuleiro[i][j].cor = (i == 0 || i == 1 || i == TAMANHO_TABULEIRO - 2 || i == TAMANHO_TABULEIRO - 1) ? BRANCO : PRETO;
            }

            // Definir número da peça (apenas para peões)
            if (tabuleiro[i][j].tipo == PEAO) {
                tabuleiro[i][j].numero = (i == 1 || i == TAMANHO_TABULEIRO - 2) ? j + 1 : -1;
            }
        }
    }
}

void exibirTabuleiro(Peca tabuleiro[TAMANHO_TABULEIRO][TAMANHO_TABULEIRO]) {
    char colunas[] = {'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'};
    int i, j;

    printf("\n   ");
    for (i = 0; i < TAMANHO_TABULEIRO; i++) {
        printf(" %c ", colunas[i]);
    }
    printf("\n");

    for (i = 0; i < TAMANHO_TABULEIRO; i++) {
        printf(" %d ", TAMANHO_TABULEIRO - i);
        for (j = 0; j < TAMANHO_TABULEIRO; j++) {
            if ((i + j) % 2 == 0) {
                printf("[X]");
            } else {
                switch (tabuleiro[i][j].tipo) {
                    case PEAO:
                        printf("[%cP%d]", (tabuleiro[i][j].cor == BRANCO) ? 'B' : 'P', tabuleiro[i][j].numero);
                        break;
                    case TORRE:
                        printf("[%cT]", (tabuleiro[i][j].cor == BRANCO) ? 'B' : 'P');
                        break;
                    case CAVALO:
                        printf("[%cC]", (tabuleiro[i][j].cor == BRANCO) ? 'B' : 'P');
                        break;
                    case BISPO:
                        printf("[%cB]", (tabuleiro[i][j].cor == BRANCO) ? 'B' : 'P');
                        break;
                    case RAINHA:
                        printf("[%cD]", (tabuleiro[i][j].cor == BRANCO) ? 'B' : 'P');
                        break;
                    case REI:
                        printf("[%cR]", (tabuleiro[i][j].cor == BRANCO) ? 'B' : 'P');
                        break;
                    default:
                        printf("[_]");
                        break;
                }
            }
        }
        printf(" %d\n", TAMANHO_TABULEIRO - i);
    }

    printf("   ");
    for (i = 0; i < TAMANHO_TABULEIRO; i++) {
        printf(" %c ", colunas[i]);
    }
    printf("\n\n");
}

