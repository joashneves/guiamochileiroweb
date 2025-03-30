Comunicação entre pessoas - A linguagem é o meio mais eficaz
Na programação de computadores - A linguagem de programação é o meio de comunicação entre o programador e o computador
Função da linguagem de programação - conecta o pensamento humano com a precisão necessária para o processamento da maquina
Linguagem de alto nível - deve incluir construções que refletem a terminologia e os elementos do problema a ser resolvido.

Linguagem de maquina é uma linguagem de baixo nível, é quando o compilador entra em ação ele passar uma linguagem de alto nível para baixo nível (linguagem da maquina)
### Compiladores
Linguagem de montagem, em que instruções e endereções de memoria adotam uma forma simbolica. Por exemplo, a instrução em linguagem de montagem - MOV X , 2

A Compilação pre-aloca na memoria salvando momentos na memoria.
### Interpretador
Traduz e  executa o codigo-fonte imediatamente, sem gerar codigo-objeto. É útil para desenvolvimento e educação, mas compiladores são preferíveis quando a velocidade é crucial.

Fazendo que o interprete aloca e interpreta as coisas durante a construção do código.

### Hibrido
Java usa um modelo hibrido combinando compilação e interpretação. O codigo-fonte é compilado para bytecode, que roda na JVM, permitindo portabilidade e otimização em tempo real.

### Arquitetura hipotetica
Eles fazem parte do conjunto de instruções de uma linguagem assembly especifica, usada para programação de baixo nivel em processadores. O objetivo dessas instruções é manipular dados diretamente na memoria e nos registradores de CPU, permitindo operações básicas como carregamento de dados, armazenamento, soma e controle de fluxo de execução

LOAD (00) : Transfere o conteudo de uma posição de memoria para um registrador

STORE(01) : Transfere o conteudo de um registrador para uma posição de memoria

ADD(10): Soma o conteudo de dois registradores e armazena o resultado em um terceiro

BZero(11): Altera o contador de programa para um endereço especifico se o registrador for zero