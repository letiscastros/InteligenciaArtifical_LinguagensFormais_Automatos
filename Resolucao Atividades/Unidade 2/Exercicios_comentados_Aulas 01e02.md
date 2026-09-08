# 1. Alfabeto
Considere: 

Σ = a,b,c

Responda:

1) Quantos símbolos existem no alfabeto? 3
2) Quais são os símbolos? a, b e c
3) O símbolo a pertence ao alfabeto? sim
4) O símbolo d pertence ao alfabeto? não
5) Escreva uma palavra formada por símbolos desse alfabeto. baba

# 2. Palavras sobre um alfabeto

Considere: 

Σ = 0,1

Classifique cada sequência como palavra válida ou não válida:

| Sequência | Válida? | Justificativa |
|---|---|---|
| `0101` |Sim|ambos pertencem ao alfabeto|
| `00110` |Sim|ambos pertencem ao alfabeto|
| `012` |Não|2 não pertence ao alfabeto|
| `111` |Sim| 1 pertence ao alfabeto|
| `10a` |Não| "a" não pertence ao alfabeto |

# 3. Pertinência de símbolos e palavras

Considere: 

Σ = 0,1

Determine se as afirmações são verdadeiras ou falsas:

1) 0 ∈ Σ - Verdadeiro, 0 existe no alfabeto.
2) 1 ∈ Σ - Verdadeiro, 1 existe no alfabeto.
3) 01 ∈ Σ - Falso, 0 e 1 existem no alfabeto mas 01 pertence ao conjunto de todas as palavras sobre Sigma.
4) 01 ∈ Σ∗ - Verdadeiro, 01 pertence ao conjunto de todas as palavras sobre Sigma.
5) 2 ∈ Σ - Falso, 2 não existe no alfabeto.
6) 101 ∈ Σ∗ - Verdadeiro, 101 pertence ao conjunto de todas as palavras sobre Sigma.
Justifique cada resposta.

# 4. Linguagem

Considere: 

L = 0, 01, 011, 0111

Determine se cada palavra pertence à linguagem:

1) 0 ∈ L - 0 pertence à linguagem.
2) 01 ∈ L - 01 pertence à linguagem.
3) 0111 ∈ L - 0111 pertence à linguagem.
4) 10 ∈ L - 10 não pertence à linguagem.
5) 111 ∈ L - 111 não pertence à linguagem.
6) 011 ∈ L - 011 pertence à linguagem.

# 5. Descrevendo uma linguagem por padrão

Considere: 

L = b^n ∣ n ≥ 1

1) Escreva as cinco primeiras palavras: b, bb, bbb, bbbb, bbbbb
2) Explique o significado de b^n: Significa a letra "b" repetida n vezes seguidas. Por exemplo, se n=3, então b³ = bbb.
3) A palavra bbbbbb pertence à linguagem? Sim. Ela tem 6 letras "b" (n=6), e como n=6 é maior ou igual a 1, ela satisfaz a condição da linguagem.
4) A palavra vazia (ε) pertence à linguagem? Não. A definição exige n ≥ 1, ou seja, pelo menos uma letra "b". Como a palavra vazia tem zero letras (n=0), ela fica de fora dessa linguagem.

# 6. Linguagem vazia e palavra vazia

Explique, com suas próprias palavras, a diferença entre:

A) L = ∅
B) L = ε

Depois responda:

Qual delas possui uma palavra? B, a palavra vazia representa uma palavra de comprimento 0.
Qual delas não possui nenhuma palavra? A, pois refere-se à um conjunto sem elementos, não possuindo nenhuma palavra.
Qual é o comprimento da palavra  ε? 0

# 7. Estrutura de uma gramática

Considere: 

G = (S, A, 0, 1, P, S)

com:

P = S → 0A, A → 1

Identifique:

1) O conjunto de variáveis.
2) O conjunto de terminais.
3) O conjunto de produções.
4) O símbolo inicial.
5) Qual palavra pode ser gerada por essa gramática?

# 8. Como ler e aplicar uma produção

Considere: 

S → 0S

Começando com S:

1) Aplique a regra uma vez:
2) Aplique a regra duas vezes:
3) Aplique a regra três vezes:
4) Escreva a sequência completa de derivação:

# 9. Derivação completa de uma palavra

Utilizando: 

G: {S → aSS → b

gere:

aaab

Escreva todos os passos da derivação.

# 10. Identificando palavras geradas por uma gramática

Considere novamente:

G: {S → 0SS → 1

Determine se cada palavra pode ser gerada:

1) 1
2) 01
3) 001
4) 0001
5) 101
6) 1001
Para as palavras que podem ser geradas, apresente a derivação completa.


