# Jogo de Batalha Naval

Este é um jogo de Batalha Naval implementado em Portugol. O objetivo do jogo é afundar todos os barcos do oponente antes que ele afunde os seus. O jogador e o computador possuem 3 barcos: um de tamanho 2 e dois de tamanho 3. O jogo é jogado em um tabuleiro de 10x10.

## Índice

- [Introdução](#introdução)
- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Como Jogar](#como-jogar)
- [Funcionamento Interno](#funcionamento-interno)
  - [Inicialização do Tabuleiro](#inicialização-do-tabuleiro)
  - [Posicionamento dos Barcos](#posicionamento-dos-barcos)
  - [Lógica de Tiro](#lógica-de-tiro)
  - [Condições de Vitória](#condições-de-vitória)
- [Exemplo de Execução](#exemplo-de-execução)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Introdução

O jogo de Batalha Naval é um clássico onde dois jogadores tentam afundar os barcos um do outro em um tabuleiro oculto. Neste projeto, o jogador compete contra o computador, que faz jogadas aleatórias. O jogador deve posicionar seus barcos no tabuleiro e, em seguida, alternar turnos com o computador, tentando adivinhar onde os barcos inimigos estão posicionados.

## Requisitos

Para executar este projeto, você precisará de:

- Portugol Studio (ou outro interpretador de Portugol)
- Um ambiente de desenvolvimento compatível com Portugol

## Instalação

1. **Baixe o Portugol Studio**: Se você ainda não tem o Portugol Studio instalado, pode baixá-lo a partir do [site oficial](http://lite.acad.univali.br/portugol/).

2. **Clone o repositório**: Use o comando abaixo para clonar o repositório do projeto:

    ```bash
    git clone https://github.com/seu-usuario/batalha-naval-portugol.git
    ```

3. **Abra o projeto**: No Portugol Studio, abra o arquivo `batalha_naval.por`.

4. **Execute o projeto**: Clique no botão de execução para iniciar o jogo.

## Como Jogar

1. **Posicionamento dos Barcos**:
   - O jogador será solicitado a posicionar seus barcos. Cada barco deve ser colocado no tabuleiro informando a coordenada inicial (X, Y) e a direção (horizontal ou vertical).
   - O jogador tem 3 barcos para posicionar: um de tamanho 2 e dois de tamanho 3.

2. **Turnos**:
   - Após posicionar os barcos, o jogador e o computador alternam turnos.
   - O jogador escolhe uma coordenada (X, Y) para atirar, tentando acertar os barcos do computador.
   - O computador também realiza tiros aleatórios no tabuleiro do jogador.

3. **Condições de Vitória**:
   - O jogo termina quando um dos jogadores afunda todos os barcos do adversário.
   - Se o jogador afundar todos os barcos do computador primeiro, ele vence. Se o computador afundar todos os barcos do jogador primeiro, o jogador perde.

## Funcionamento Interno

### Inicialização do Tabuleiro

O tabuleiro de cada jogador é representado por uma matriz de 10x10, inicializada com zeros. Cada célula pode conter:
- `0`: Água (nenhum barco)
- `1`: Parte de um barco
- `2`: Barco atingido
- `3`: Tiro na água

### Posicionamento dos Barcos

- **Jogador**: O jogador posiciona seus barcos manualmente, escolhendo a coordenada inicial e a direção (horizontal ou vertical).
- **Computador**: O computador posiciona seus barcos aleatoriamente, garantindo que eles não se sobreponham.

### Lógica de Tiro

Quando um tiro é realizado:
- Se a célula contém `1`, o tiro é um acerto, e a célula é marcada como `2`.
- Se a célula contém `0`, o tiro é um erro, e a célula é marcada como `3`.

### Condições de Vitória

O jogo verifica após cada turno se todos os barcos de um jogador foram afundados. Se todos os barcos forem atingidos, o jogo termina e o vencedor é declarado.

## Exemplo de Execução

Aqui está um exemplo de como o jogo pode se desenrolar:

```plaintext
Posicione o barco de tamanho 2:
Informe a coordenada X inicial (0-9): 2
Informe a coordenada Y inicial (0-9): 3
Informe a direção (H para horizontal, V para vertical): H

Posicione o barco de tamanho 3:
Informe a coordenada X inicial (0-9): 5
Informe a coordenada Y inicial (0-9): 5
Informe a direção (H para horizontal, V para vertical): V

Posicione o barco de tamanho 3:
Informe a coordenada X inicial (0-9): 7
Informe a coordenada Y inicial (0-9): 1
Informe a direção (H para horizontal, V para vertical): H

Seu turno! Informe a coordenada X para atirar (0-9): 4
Informe a coordenada Y para atirar (0-9): 4
Você atirou na água em (4, 4).

Computador atirou na água em (7, 8).

...

Parabéns! Você afundou todos os barcos do computador!
