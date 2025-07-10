Posicionamento de Navios – Nível Novato
Este repositório demonstra como posicionar dois navios em um tabuleiro de Batalha Naval usando matrizes 2D em C. Um navio será colocado horizontalmente e outro verticalmente. Ao final, exibimos no console:

As coordenadas de cada parte dos navios

A visualização completa do tabuleiro.

Objetivos:
Posicionar um navio horizontal de tamanho configurável

Posicionar um navio vertical de tamanho configurável

Utilizar uma matriz bidimensional para representar o tabuleiro

Exibir, via printf, as coordenadas de cada parte dos navios

Mostrar o tabuleiro completo com 0 (vazio) e 1 (navio)

Requisitos Funcionais:
Valores de posição e tamanho definidos por variáveis no código

Uso de matrizes para armazenar o estado do tabuleiro

Exibição clara das coordenadas e do tabuleiro

Requisitos Não Funcionais:
Código bem documentado para fácil manutenção

Organização lógica em seções comentadas

Execução eficiente em tabuleiros de até 10×10 células

Como Compilar e Executar:
bash
gcc main.c -o batalha_naval
./batalha_naval
main.c
c
#include <stdio.h>

#define ROWS 5       // Número de linhas do tabuleiro
#define COLS 5       // Número de colunas do tabuleiro

int main(void) {
    // 1. Inicializa o tabuleiro com zeros (vazio)
    int board[ROWS][COLS] = {0};

    // 2. Definição dos navios
    // Navio horizontal
    int startRowH = 1;   // linha inicial
    int startColH = 0;   // coluna inicial
    int lengthH   = 3;   // tamanho do navio horizontal

    // Navio vertical
    int startRowV = 0;   // linha inicial
    int startColV = 4;   // coluna inicial
    int lengthV   = 4;   // tamanho do navio vertical

    // 3. Posiciona o navio horizontal
    for (int j = 0; j < lengthH; j++) {
        board[startRowH][startColH + j] = 1;
    }

    // 4. Posiciona o navio vertical
    for (int i = 0; i < lengthV; i++) {
        board[startRowV + i][startColV] = 1;
    }

    // 5. Exibe as coordenadas de cada parte dos navios
    printf("Navio Horizontal (tamanho %d) - coordenadas:\n", lengthH);
    for (int j = 0; j < lengthH; j++) {
        printf("  Parte %d: (linha %d, coluna %d)\n",
               j + 1, startRowH, startColH + j);
    }

    printf("\nNavio Vertical (tamanho %d) - coordenadas:\n", lengthV);
    for (int i = 0; i < lengthV; i++) {
        printf("  Parte %d: (linha %d, coluna %d)\n",
               i + 1, startRowV + i, startColV);
    }

    // 6. Exibe o tabuleiro completo
    printf("\nTabuleiro (0 = vazio, 1 = navio):\n");
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++) {
            printf("%d ", board[i][j]);
        }
        printf("\n");
    }

    return 0;
}
Explicação do Código:
Inicialização A matriz board recebe zeros em todas as posições.

Definição dos Navios Variáveis para linha, coluna e comprimento permitem alterar facilmente posição e tamanho.

Posicionamento:

Laço horizontal ajusta colunas mantendo a mesma linha.

Laço vertical ajusta linhas mantendo a mesma coluna.

Exibição de Coordenadas Percorremos somente as células ocupadas por cada navio e imprimimos sua posição.

Visualização do Tabuleiro Exibe toda a matriz, deixando evidente onde cada navio foi posicionado.

Próximos Passos:
Permitir entrada de coordenadas pelo usuário via scanf

Validação de sobreposição ou saída do tabuleiro

Implementar mais navios e lógica de “tiro”
