---
dg-publish: true
---
- **Conjunto FIRST:** O FIRST conjunto de um não terminal contém todos os símbolos terminais que podem aparecer no início de qualquer string derivada desse não terminal. Em outras palavras, ele nos diz quais símbolos terminais são possíveis ao expandir um não terminal.
- **Conjunto FOLLOW:** O conjunto FOLLOW de um não terminal contém todos os símbolos terminais que podem aparecer imediatamente após esse não terminal em qualquer derivação. Ele ajuda a identificar o que pode seguir um não terminal na gramática e é essencial para lidar com produções em que um não terminal está no final de uma regra.
# FIRST(X)
O conjunto FIRST(X) é uma coleção de símbolos terminais (e possivelmente ε) que podem aparecer como o símbolo mais à esquerda quando expandimos X em uma derivação de uma determinada gramática.
## 1 - Quando X é terminal
Se X for um símbolo terminal (por exemplo, 'a' ou 'b'), o conjunto FIRST(X) simplesmente contém o próprio X, já que um terminal sempre começa consigo mesmo.
- _Exemplo: Se X = a, então FIRST(a) = {a}._
## 2 - Quando X tem apenas uma regra de produção do tipo X → aY:
Por exemplo A → a B, o PRIMEIRO conjunto de A é o primeiro caractere não terminal.

Exemplo:
```bash
> `A → a B`

Aqui, FIRST(A → a B) é apenas {a} porque 'a' é o primeiro símbolo terminal no lado direito da produção.
```

## 3 - Quando X tem múltiplas regras de produção:
Se X for um não terminal (por exemplo, A ou B), o conjunto FIRST(X) inclui todos os símbolos terminais que podem ser o primeiro símbolo de qualquer string derivada de X. Isso significa que, para cada regra de produção de X, você observa qual pode ser o primeiro 
símbolo dessa regra.

Exemplo:
```bash
> `A → a B`  
> `A → b`  
> `A → ε`

 Aqui, FIRST(A) = {a, b, ε} porque:

- O primeiro símbolo na primeira produção A → a B é 'a'.
- O primeiro símbolo na segunda produção A → b é 'b'.
- A terceira produção A → ε significa que A pode derivar uma string vazia, então ε é incluído.
```

## 4 - Quando X é uma sequência de não terminais:
Se X for uma string composta de terminais e/ou não terminais (como ABC), começamos com o símbolo mais à esquerda e usamos seu FIRST conjunto.

Para calcular FIRST(X), você considera FIRST(A). Se A puder derivar ε (ou seja, a string vazia), então você também considera FIRST(B), e assim por diante. Se A e B puderem derivar ε, você também precisa considerar FIRST(C).

Exemplo:
```bash
> `X → A B C`  
> A→a∣ε  
> B→b∣ε  
> C→c∣d

O FIRST(X) é {a,b,c,d}.
Isto ocorre porque:
- A contribui com a e ε.
- B contribui com b e ε.
- C contribui com c e d. Como A e B podem derivar ε, incluímos os primeiros símbolos de C.

```

# FOLLOW(X)
O conjunto FOLLOW(X) contém todos os símbolos terminais que podem aparecer imediatamente após o X não terminal em qualquer string válida derivada da gramática. Ele é usado na análise sintática para decidir quais símbolos podem seguir um determinado X não terminal em uma derivação.

## 1 - Quando X é o símbolo inicial da gramática:
Se X for o símbolo inicial (por exemplo, S), o conjunto FOLLOW(S) sempre inclui o marcador especial de fim de entrada `$`para indicar que nada vem depois do símbolo inicial em uma string completa.

Exemplo:
```bash
`Start Symbol = S`  
`FOLLOW(S) = { $ }`
```
## 2 - Quando X aparece antes de um terminal:
Se X for seguido por um símbolo terminal em uma regra de produção, esse símbolo terminal será adicionado a FOLLOW(X).

Exemplo:
```bash
> `A → a B c`

Aqui, B é seguido por c, então c está em FOLLOW(B).
```

## 3 - Quando X aparece antes de um não terminal:
Se **X** for seguido por um não terminal (por exemplo, B), o conjunto FIRST(B) é adicionado a FOLLOW(X). No entanto, se B puder derivar ε (string vazia), então

- FOLLOW(X) inclui o FIRST terminal ou não terminal (excluindo ε) que está depois de B.
- Se não houver nada depois de B, então FOLLOW(X) inclui o FOLLOW do lado esquerdo não terminal da regra de produção.

Exemplo:
```bash
> `A → a X B`  
> `B → b |` e

Se FIRST(B) = {b, ε}, então:

- b é adicionado a FOLLOW(X).
- Como B pode derivar ε, FOLLOW(A) também será incluído em FOLLOW(X).
```
## 4 - Quando X aparece no final de uma regra de produção:
Se X aparecer no final de uma regra de produção (por exemplo, A → BX), então FOLLOW(A) será adicionado a FOLLOW(X) porque tudo o que vier depois de A na string também deve vir depois de X.
Exemplo:
```bash
> `A → B X`
```
Aqui, tudo em FOLLOW(A) também deve ser incluído em FOLLOW(X).

# FIRST conjunto na analise de sintaxe
O conjunto FIRST é usado na análise sintática para identificar quais símbolos terminais podem aparecer no início de strings derivadas de um não terminal. É crucial para analisadores LL e LR, ajudando-os a decidir quais regras aplicar.

Para calcular o PRIMEIRO conjunto:

1. Adicione o próprio terminal ao PRIMEIRO conjunto para todos os terminais.
2. Para não terminais, adicione o PRIMEIRO terminal do lado direito de suas produções.
3. Repita até que não seja possível adicionar mais símbolos.

Em analisadores LL, se o próximo símbolo de entrada corresponder ao PRIMEIRO conjunto de um não terminal, essa regra pode ser aplicada com segurança. O PRIMEIRO conjunto também é usado no cálculo do conjunto SEGUINTE, que identifica o que pode vir imediatamente após um não terminal em uma gramática.

## Regras para calcular o FIRST conjunto
1. Se x for um terminal, então FIRST(x) = { 'x' }
2. Se x-> ε for uma regra de produção, então adicione ε a FIRST(x).
3. Se X->Y1 Y2 Y3….Yn é uma produção,   
    1. PRIMEIRO(X) = PRIMEIRO(Y1)
    2. Se FIRST(Y1) contém ε então FIRST(X) = { FIRST(Y1) – ε } U { FIRST(Y2) }
    3. Se FIRST(Yi) contiver ε para todos os i = 1 a n, então adicione ε a FIRST(X).
Exemplo :
```bash
Regras de produção da gramática
E  -> TE’  
E’ -> +T E’| ε  
T  -> F T’  
T’ -> *F T’ |  ε  
F  -> (E) | id  
  
FIRST sets
FIRST(E) = FIRST(T) = { ( , id }  
FIRST(E’) = { +, ε}  
FIRST(T) = FIRST(F) = { ( , id }  
FIRST(T’) = { *, ε }  
FIRST(F) = { ( , id }

Regras de produção da gramática
S -> ACB | Cbb | Ba  
A -> da | BC  
B -> g | ε  
C -> h | ε  
  
FIRST sets
FIRST(S) = FIRST(ACB) U FIRST(Cbb) U FIRST(Ba)  
         = { d, g, h, b, a,  ε}  
FIRST(A) = { d } U FIRST(BC)   
         = { d, g, h,  ε }  
FIRST(B) = { g ,  ε }  
FIRST(C) = { h ,  ε }
```
> 1. A gramática usada acima é a Gramática Livre de Contexto ( [CFG](https://www-geeksforgeeks-org.translate.goog/what-is-context-free-grammar/?_x_tr_sl=en&_x_tr_tl=pt&_x_tr_hl=pt&_x_tr_pto=tc)). A sintaxe da maioria das linguagens de programação pode ser especificada usando CFG.
> 2. CFG é do formato A -> B, onde A é um único Não-Terminal e B pode ser um conjunto de símbolos gramaticais (ou seja, Terminais e Não-Terminais)

# Conjunto FOLLOW na Análise de Sintaxe
O conjunto FOLLOW na Análise de Sintaxe é um grupo de símbolos que pode vir logo após um não terminal em uma gramática. Ele ajuda os analisadores a descobrir o que deve aparecer em seguida na entrada enquanto verificam se a gramática está correta. O conjunto FOLLOW é importante para a construção de tabelas de análise, especialmente em analisadores LL(1), que o utilizam para decidir como processar regras durante a verificação de sintaxe.  
Por exemplo, se você estiver analisando uma frase em uma linguagem de programação, o conjunto FOLLOW informa ao analisador quais símbolos válidos podem seguir uma regra ou variável específica. Ele também inclui o símbolo de fim de entrada ( `$`) para mostrar quando a string de entrada termina. Isso torna o conjunto FOLLOW uma ferramenta essencial na criação de analisadores confiáveis ​​para linguagens de programação.

## Regras para calcular o conjunto FOLLOW: 
1) FOLLOW(S) = { $ } // onde S é o Não Terminal inicial  
  
2) Se A -> pBq for uma produção, onde p, B e q são quaisquer símbolos gramaticais,  
então tudo em FIRST(q) exceto Є está em FOLLOW(B).  
  
3) Se A->pB for uma produção, então tudo em FOLLOW(A) está em FOLLOW(B).  
  
4) Se A->pBq for uma produção e FIRST(q) contiver Є,  
então FOLLOW(B) contém { FIRST(q) – Є } U FOLLOW(A)

Exemplo :
```bash
Regras de produção
E -> TE’  
E’ -> +T E’|Є  
T -> F T’  
T’ -> *F T’ | Є  
F -> (E) | id  
  
FIRST set  
FIRST(E) = FIRST(T) = { ( , id }  
FIRST(E’) = { +, Є }  
FIRST(T) = FIRST(F) = { ( , id }  
FIRST(T’) = { *, Є }  
FIRST(F) = { ( , id }  
  
FOLLOW Set
FOLLOW(E)  = { $ , ) }  // Note  ')' is there because of rule 3 (the propagation of FOLLOW(E) through the non-terminal E’)  
FOLLOW(E’) = FOLLOW(E) = {  $, ) }  // See 1st production rule  
FOLLOW(T)  = { FIRST(E’) – Є } U FOLLOW(E’) U FOLLOW(E) = { + , $ , ) }  
FOLLOW(T’) = FOLLOW(T) =      { + , $ , ) }  
FOLLOW(F)  = { FIRST(T’) –  Є } U FOLLOW(T’) U FOLLOW(T) = { *, +, $, ) }

// Exemplo 2 :
Production Rules:
S -> aBDh  
B -> cC  
C -> bC | Є  
D -> EF  
E -> g | Є  
F -> f | Є  
  
FIRST set
FIRST(S) = { a }  
FIRST(B) = { c }  
FIRST(C) = { b , Є }  
FIRST(D) = FIRST(E) U FIRST(F) = { g, f, Є }  
FIRST(E) = { g , Є }  
FIRST(F) = { f , Є }  
  
FOLLOW Set
FOLLOW(S) = { $ }   
FOLLOW(B) = { FIRST(D) – Є } U FIRST(h) = { g , f , h }  
FOLLOW(C) = FOLLOW(B) = { g , f , h }  
FOLLOW(D) = FIRST(h) = { h }  
FOLLOW(E) = { FIRST(F) – Є } U FOLLOW(D) = { f , h }  
FOLLOW(F) = FOLLOW(D) = { h }

// Exemplo 3 :
Production Rules:
S -> ACB|Cbb|Ba  
A -> da|BC  
B-> g|Є  
C-> h| Є  
  
FIRST set 
FIRST(S) = FIRST(A) U FIRST(B) U FIRST(C) = { d, g, h, Є, b, a}  
FIRST(A) = { d } U {FIRST(B)-Є} U FIRST(C) = { d, g, h, Є }  
FIRST(B) = { g, Є }  
FIRST(C) = { h, Є }  
  
FOLLOW Set
FOLLOW(S) = { $ }  
FOLLOW(A)  = { h, g, $ }  
FOLLOW(B) = { a, $, h, g }  
FOLLOW(C) = { b, g, $, h }

```

> 1. Є como FOLLOW não significa nada (Є é uma string vazia).
> 2. $ é chamado de marcador final, que representa o fim da string de entrada, sendo, portanto, usado durante a análise para indicar que a string de entrada foi completamente processada.
> 3. A gramática usada acima é [a Gramática Livre de Contexto](https://www-geeksforgeeks-org.translate.goog/what-is-context-free-grammar/?_x_tr_sl=en&_x_tr_tl=pt&_x_tr_hl=pt&_x_tr_pto=tc) (CFG). A sintaxe de uma linguagem de programação pode ser especificada usando CFG.
> 4. CFG é do formato A -> B, onde A é um único Não-Terminal e B pode ser um conjunto de símbolos gramaticais. (ou seja, Terminais e Não-Terminais)