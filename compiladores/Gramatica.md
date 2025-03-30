A gramatica formal é usada para definir a estrutura das linguagens de programação. Ela descreve como sequencia de simbolos pode ser gerada de forma valida. A gramatica é composta por quatro elementos principais: V,T,P,S

Uma Gramatica é representada como um conjunto G = (V, T, P, S) onde:
- V (variavel ou não termial) : Representa categorias sintáticas, como expressões ou comandos
- T (Terminais) : São os simbolos finais da linguagem (Palavra-chave, operadores, identificadores)..
- P (Produções) : São regras que definem como os símbolos não terminais podem ser substituídos por outros simbolos.
- S (simbolos inicial) : É o ponto de partida para derivas expressões validas na linguagens
### Exemplos de gramatica:
- G = ({e}, {0,1,+}, P, E)
- V = {e} -> O unico não terminal é "E" (Expressão).
- T = {0, 1} -> Os terminais são os numeros 0, 1 e o operador +
- P = {e -> E + E | 0 | 1 }
	- Uma expressão pode ser formada por duas expressões unidas pelo +
	- ou pode ser diretamente 1 | 0
- S = E -> O símbolo inicial é E