---
dg-publish: true
---
## Alfabeto 
**Importancia das cadeias de caracteres:**
- Fundamentais para diversas aplicações em ciencias da computação
- Utilizadas em processamento de texto, analise de dados, programação e diversas areas.
**Definição de alfabeto:**
- Um alfabeto é um conjunto finito e não vazio de simbolos ou caracteres
- Pode varia de acordo com a aplicação (ex: letas, numeros, caracteres especiais, notação Σ )
- Alfabeto
- > Binario: Σ = {0, 1}
- > Romano: Σ = {a,b,c...,z }
- > Decimal: Σ = {0,1,2,3,4,5,6,7,8,9}
## Palavra
- Uma palavra, cadeia de caracteres ou sentença é uma finita de simbolos finita de simbolos de alfabeto.
- Os simbolos são escritos um apos o outro, sem separação por virgulas
- Notação : W
- Palavra vazia: &
- > é uma palavra sem simbolos, ou seja, de comprimento de **ZERO**
Exemplos de palavras sobre diferentes alfabetos
- Alfabeto binario Σ = {0, 1}
- > palavra : 01010111
- Alfabeto romano Σ = { a, b, c, d..., z}
- > Palavra : MAMAMIA
- > Σ = {a, b} : aa, bb, aabb, aaa
## Prefixo
- Um prefixo de uma palavra é qualquer sequencia de simbolos iniciais da palabra
- Pode variar de um unico simbolo ate a palavra completa .
- > Exemplo : prefixo da palavra "Mamamia"
	- > E, M, MA, MAM, MAMA, MAMAM, MAMAMI, MAMAMIA.
## Sufixo
- Um sufixo de uma palavra é qualquer sequencia de simbolos finais da palavras
- Assim como os prefixos, pode virar de um único símbolo ate a palavra completa.
	- Exemplo : Sufixos da palavra "Mamamia"
	- > E, A, IA, MiA, AMIA, MAMIA, Amamia, Mamamia
## SubPalavra
A subpalavra de uma palavra é qualquer sequencia de simbolos contigua da palavra.
- > M, a , m, a, m, i, a
- > MA, AM, MA, AM, MI, IA
- > MAM, AMA, AMI, MIA
- > MAMA, AMAM, MAMI, AMIA
- > MAMAM, AMAMIA, MAMIA
- > MAMAMI, AMAMIA
- > MAMAMIA
## Comprimento 
Notação : |W|
- ex : MAMAMIA = |7|
- |&| = 0
## Concatenação 
Associação de duas palavras
- Operação binaria
- Justaposição de uma palavra com a outra. Ex: po te - pote
- A operação de concatenação satisfaz as seguintes propriedades (**suponha V, WeT palavras**):
- > Associatividade -> V (WT) = (VW)T
- > Elemento neutro à esquerda e à direita -> EW = W = WE
- > Ex = Σ = {a, b} para V = baaab, W = bb
	- > VW = baaabbb
	- > VE = baaab
A operação de concatenação sucessiva é definida indutivamente apartir da concatenação binaria: 
- a² = aa
- a^0 = e
- b²a³ = bbaaaa
O Conjunto de todas palavras possiveis sobre Σ é representado por Σ*, enquanto que Σ+ representa o conjunto de todas as palavras possiveis sobre Σ com exceção da palavra vazia, ou seja : Σ+ = Σ* - {e}
## Linguagem formal
- Uma linguagem formal e o conjunto 0 de palavras sobre um alfabeto ou um subcojunto de Σ*
_Notação : L_
- O conjunto vazio e o conjunto formação pela palavra vazia são linguagens sobre : Σ : logo, 0 /= {e}
- o conjunto de palíndromos (palavras que tem a mesma leitura da esquerda para direita e vice-versa) sobre Σ é um exemplo de linguagem infinita
- > E, a, b, aa, bb, aaa, aba, bab, bbb, aaaa, abba