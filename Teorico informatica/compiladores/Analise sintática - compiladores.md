---
dg-publish: true
---
# Fatoração à Esquerda
- Fatorar à esquerda a produção A → α1α2 ...αn é introduzir um novo não-terminal X e, para algum i, substituí-la por
- A → α₁α₂ ...αᵢX e
- X → αᵢ+₁...αₙ.
- A fatoração à esquerda permite eliminar a indecisão sobre qual produção aplicar quando duas ou mais produções iniciam com a mesma forma sentencial.
- Por exemplo, αβ₁ | αβ₂ seria eliminada fatorando as mesmas para
-  A → αX e X → β₁ | β₂ .
-  Para a análise descendente preditiva, é necessário que a gramática esteja fatorada à esquerda.
- A → α₁α₂ ...αᵢX
- w = Aα₄
-  Eliminar o não determinismo da gramática.
-  Postergando a decisão.
-  A → αX'
- X' → α₁ | α₂| α₄
# Análise Descendente
- A análise descendente (top-down) de uma sentença (ou programa) pode ser vista como uma tentativa de construir uma árvore de derivação em pré-ordem (da esquerda para a direita) para a sentença em questão:
-  Cria a raiz e, a seguir, cria as subárvores filhas, da esquerda para a direita.
- Esse processo produz uma derivação mais à esquerda da sentença em análise.
- **Três tipos de analisadores sintáticos descendentes:**
- Recursivo com retrocesso (backtracking).
- Recursivo preditivo.
- Tabular preditivo.
# Análise Recursiva com Retrocesso
- Faz a expansão da árvore de derivação a partir da raiz, expandindo sempre o não-terminal mais à esquerda.
- Quando existe mais de uma regra de produção para o não-terminal a ser expandido, a opção escolhida é função do símbolo corrente na fita de entrada (token sob o cabeçote de leitura).
- Se o token de entrada não define univocamente a produção a ser usada, então todas as alternativas vão ser tentadas até que se obtenha sucesso (ou até que a análise falhe irremediavelmente).
- É bom relembrar que a presença de recursividade à esquerda em uma gramática ocasiona problemas para analisadores descendentes:
- Como a expansão é sempre feita para o não-terminal mais à esquerda, o analisador irá entrar num ciclo infinito se houver esse tipo de recursividade.
-  Exemplo da sentença [ a ] sobre a gramática:
- G = ({S, L}, {a, ;, [, ]}, {S → a | [ L ], L → S ; L | S}, S)
- Ao processo de voltar atrás no reconhecimento e tentar produções alternativas dá-se o nome de retrocesso ou backtracking.
- Tal processo é ineficiente, pois leva à repetição da leitura de partes da sentença de entrada e, por isso, em geral, não é usado no reconhecimento de linguagens de programação:
- Como o reconhecimento é, geralmente, acompanhado da execução de ações semânticas (por exemplo, armazenamento de identificadores na Tabela de Símbolos), a ocorrência de retrocesso pode levar o analisador sintático a ter que desfazer essas ações.
- Outra desvantagem dessa classe de analisadores é que, quando ocorre um erro, fica difícil indicar com precisão o local do erro, devido à tentativa de aplicação de produções alternativas.
# Conjunto FIRST
Se α é uma forma sentencial (sequência de símbolos da gramática), então FIRST(α) é o conjunto de terminais que iniciam formas sentenciais derivadas a partir de α. Se α →* ε então a palavra vazia também faz parte do conjunto:
- **Se x é terminal**, então FIRST(x) = {x}.
- **Se X → ε é uma produção**, então adicione ε a FIRST(X).
- **Se X → Y₁Y₂ ...Yk é uma produção e,** para algum i, todos Y₁ , Y₂ , ..., Yᵢ-₁ derivam ε, então FIRST(Yᵢ) está em FIRST(X), juntamente com todos os símbolos não ε de FIRST(Y₁), FIRST(Y₂ ), ..., FIRST(Yᵢ-₁). O símbolo ε será adicionado a FIRST(X) apenas se todo Yj (j=1, 2, ..., k) derivar ε.
# Conjunto FOLLOW
A função FOLLOW é definida para símbolos não-terminais.
- Conjunto que indica quais símbolos terminais que podem aparecer imediatamente após ou à direita de um não terminal.
- Se E é o símbolo de partida da gramática e $ o marcador de fim da entrada, acrescente $ no Follow(E)
- Se A → αBβ, acrescente todos os símbolos do First(β), exceto ε, no Follow(B)
- Se A → αB ou A → αBβ e First(β) contém ε inclua o Follow (A) em Follow(B).

```bash
G = ({E, E', T, T', F}, {~, &, =, id}, P, S), onde
P = {E → TE', E' → ~TE' | ε, T → FT', T' → & FT' | ε, F → =F | id}


FIRST(E) = {=, id}		FOLLOW(E) = {$}
FIRST(E') = {~ , ε}		FOLLOW(E') = {$}
FIRST(T) = {=, id}		FOLLOW(T) = {~,$}
FIRST(T') = {&, ε}		FOLLOW(T') = {~,$}
FIRST(F) = {=, id}      FOLLOW(F) = {&,~,$}
```

# Análise Preditiva Tabular
- É possível construir analisadores preditivos não recursivos que utilizam uma pilha explícita ao invés de chamadas recursivas.
- Esse tipo de analisador implementa um autômato de pilha controlado por uma tabela de análise.
- O princípio do reconhecimento preditivo é a determinação da produção a ser aplicada, cujo lado direito irá substituir o símbolo não-terminal que se encontra no topo da pilha.
- O analisador busca a produção a ser aplicada na tabela de análise, levando em conta o não-terminal no topo da pilha e o token sob o cabeçote de leitura.
- Tabela que relaciona os não terminais nas linhas com os terminais nas colunas.
- Para cada produção A → α de G, execute os passos a seguir para criar a linha A da tabela M:
- Para cada terminal a de FIRST(α), adicione a produção A → α a M[A, a].
- Se ε pertence ao FIRST(α), inclua A → α M[A, a] para cada terminal i pertencente ao Follow(α).
