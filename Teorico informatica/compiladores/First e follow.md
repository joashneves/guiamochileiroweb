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