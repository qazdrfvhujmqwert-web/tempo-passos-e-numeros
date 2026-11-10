# Tempo, passos e números

Explicação de como um tempo infinito refuta uma sentença `Π⁰₁` falsa, e de como a matemática transforma passos infinitos num número sobre o qual uma pergunta finita pode decidir. O texto cobre a hipótese de Riemann e a conjectura binária de Goldbach. Nenhuma das duas fica decidida aqui.

Data: 2026-11-10.

## Estado

- A hipótese de Riemann permanece aberta.
- A conjectura binária de Goldbach permanece aberta.
- Goldbach fraco (todo ímpar maior ou igual a 7 é soma de três primos) é teorema de Helfgott. É outro enunciado.
- `implies_rh` é falso. `implies_goldbach` é falso.
- Um prefixo finito de checagens é um certificado. O quantificador universal continua aberto.
- Este arquivo é uma explicação. O veredito nunca é `proved`.

## 1. A pergunta

Com tempo infinito e passos infinitos seria possível refutar? Como se representa o tempo e o número de passos? Como se abstrai esse processo para criar números novos? O que, nessa abstração, se observa de verdade?

A resposta curta tem duas metades.

Tempo infinito, no relógio dos inteiros `n = 0, 1, 2, …`, refuta a hipótese de Riemann se ela for falsa, e refuta Goldbach binário se ele for falso. O mesmo tempo infinito não entrega a prova se o enunciado for verdadeiro. Nenhuma etapa finita lê a cauda, e o estágio `ω`, em que todos os inteiros já teriam sido visitados, não é uma observação.

A prova, quando existe, é um texto finito. O gesto que substitui a sequência infinita por uma pergunta finita é a criação de um número: um real, um `p`-ádico, uma série, um adele, uma constante, um ordinal. A observação volta a ser finita: um intervalo, um resíduo, um coeficiente, um contorno, um produto de primos.

## 2. Por que a refutação é finita

Uma sentença `Π⁰₁` tem a forma `para todo n, P(n)`, com `P` decidível em cada instância. A refutação é um único `n` em que `P(n)` falha. A prova é um argumento finito que amarra todos os `n` de uma vez.

A hipótese de Riemann é `Π⁰₁`.

Lagarias (2002) dá a forma elementar: para todo inteiro `n > 1`,

```text
sigma(n) <= H_n + exp(H_n) log(H_n)
```

com igualdade só em `n = 1`. Aqui `sigma(n)` é a soma dos divisores e `H_n = 1 + 1/2 + … + 1/n`.

Robin (1984) dá a forma equivalente: para todo inteiro `n > 5040`,

```text
sigma(n) < e^γ n log log n
```

com `γ` a constante de Euler-Mascheroni. Em `n = 5040` a desigualdade de Robin falha por um fato aritmético finito. Esse fato não decide a hipótese. O equivalente começa depois de 5040.

Kreisel já tinha reescrito a hipótese como `Π⁰₁`. Apesar de `e^γ` e de `log`, a comparação em cada `n` reduz-se a uma computação com precisão finita. François G. Dorais registrou no MathOverflow que a passagem é rotineira a partir do artigo de Lagarias.

Goldbach binário também é `Π⁰₁`. Para todo par `n >= 4` existe um primo `p <= n` tal que `n - p` é primo. O quantificador existencial está limitado por `n`. Primalidade é decidível. A matriz inteira é decidível.

Da classificação segue a assimetria, válida em ZFC e, para a forma de Lagarias, no terreno em que a equivalência se formaliza:

- Se a sentença é falsa, algum `n` falha. Um programa que percorre `n = 1, 2, 3, …` imprime `NO` nesse `n` e pára. A parada é uma prova de refutação, porque a computação finita se formaliza.
- Se a sentença é verdadeira, o mesmo programa não pára. Verdade de um `Π⁰₁` não fabrica sozinha um texto finito dentro de uma teoria fixa. A hipótese de Riemann pode, em princípio, ser verdadeira e sem prova em ZFC. Goldbach binário idem. Essa metade permanece aberta.

Há um reforço publicado por Broughan (2024) que afirma decidibilidade da hipótese em PA via a análise de Takeuti. Esse reforço vai além do consenso assentado no MathOverflow. O que está assentado é a metade de cima: falsidade implica refutação finita e provável. A metade de baixo, verdade sem prova numa teoria fixa, continua possível enquanto não houver prova.

## 3. A máquina que espera

Aaronson e Yedidia (2016) escreveram a espera como hardware. Uma máquina de Turing de fita em branco pára se e só se a hipótese de Riemann é falsa. Outra pára se e só se Goldbach é falsa. Uma terceira, chamada Z, pára se e só se ZFC é inconsistente.

Os tamanhos publicados em 2016, no relato da New Scientist e no anúncio de Aaronson:

| máquina | estados | pára exatamente quando |
|---|---:|---|
| Riemann | 5372 | a hipótese de Riemann é falsa |
| Goldbach | 4888 | Goldbach binário é falso |
| Z | 7918 | ZFC é inconsistente |

O número de estados mede o tamanho do buscador explícito. Não mede a dificuldade do fato. Aaronson, em *The Busy Beaver Frontier*, cita uma máquina binária posterior de 744 estados para a hipótese de Riemann. Um preprint de setembro de 2026 (Shunia, arXiv:2609.30306) descreve uma máquina de 120 estados no mesmo modelo e pede auditoria ponta a ponta. Matiyasevich deu ainda outra forma: uma máquina de registradores com 24 registradores e 128 instruções que não pára se e só se a hipótese é verdadeira, a partir da reformulação `Π⁰₁`.

Olhar a máquina correr é olhar o tempo. Halt é refutação. Ausência de halt, vista de dentro da execução, é indistinguível de "ainda não".

Completar `ω` passos, no sentido de Cantor, decide a sentença: a conjunção de todas as checagens finitas é o `para todo`. Ninguém ocupa o estágio `ω`. O que se observa é sempre um prefixo.

## 4. Três relógios

O tempo e o número de passos aparecem em três relógios. Só o terceiro cria um objeto sobre o qual uma pergunta finita substitui o quantificador.

**Relógio potencial.** O passo é `n ↦ n+1`. É o tempo de Aristóteles, de Brouwer e da máquina de Turing. Cada observação é um inteiro. O próximo passo sempre existe. O conjunto de todos os passos não é um dado que se segura na mão.

**Relógio ordinal.** Gentzen mede a força da indução por ordinais até `ε₀`. O número de passos de uma prova deixa de ser um inteiro e vira um ordinal nomeado por um texto finito. A prova continua finita. O ordinal é a abstração da duração. Uma prova da hipótese de Riemann seria um texto cujo ordinal de prova é algum `α`. Esse `α` não está nomeado.

**Relógio completo.** Uma regra dá o próximo termo, e uma relação de equivalência cola as sequências com o mesmo limite. O objeto novo é a classe de equivalência. A observação volta a ser finita. É neste relógio que a matemática fabrica número a partir de tempo.

## 5. Como o tempo vira número

| processo infinito | número que ele vira | o que se observa de verdade |
|---|---|---|
| sequência de Cauchy de racionais | um real | um intervalo racional |
| sistema coerente de resíduos `mod p^k` | um inteiro `p`-ádico | o resíduo `mod p^k` |
| coeficientes `a_n` | uma série formal ou uma série de Dirichlet | o coeficiente `n`, ou uma soma parcial |
| todos os lugares de `Q` juntos | um adele | um lugar de cada vez, com precisão finita |
| ordenadas dos zeros, deformadas pelo calor | a constante de de Bruijn–Newman `Λ` | uma cota `Λ <= c` ou `Λ >= 0` |
| todos os `r_2(n)` de Goldbach | a série `(∑_p x^p)^2` | um coeficiente |
| expoentes críticos `ε ↓ 0` | o próximo número colossalmente abundante | um produto finito de potências de primos |
| duração de uma indução | um ordinal, por exemplo `ε₀` | o nome finito do ordinal |

O inteiro hipernatural é a armadilha desta tabela. Overspill, consequência de o conjunto dos inteiros padrão não ser definível num modelo não padrão da aritmética de Peano: uma propriedade de primeira ordem verdadeira em todo inteiro padrão também vale em algum inteiro infinito. Um fracasso que vivesse só depois de todos os `n` padrão não é contraexemplo da sentença padrão. Inventar "o passo infinito" como número novo não refuta a hipótese de Riemann, não refuta Goldbach, e não os prova. Empurra o corte para um sítio que a sentença `Π⁰₁` não vê.

A criação legítima de número pede uma regra do próximo termo e um módulo de convergência. Sem o módulo, o limite de "ainda não apareceu contraexemplo" não é o certificado "não existe contraexemplo". Com o módulo, as aproximações colam num real, e apertar o intervalo é uma observação.

## 6. O que se observa de verdade

Cinco observações, todas finitas. O resto é embalagem.

### 6.1 Um inteiro

`sigma(n)` calcula-se pelo produto sobre a fatoração. `H_n` é racional. A comparação com o envelope usa precisão finita. Um único `n > 5040` com `G(n) >= e^γ`, ou um único `n` que viole Lagarias, mata a hipótese de Riemann. Um único par `n >= 4` com `r_2(n) = 0` mata Goldbach binário.

`G(n) = sigma(n) / (n log log n)`.

### 6.2 Um campeão gerado, não varrido

Gronwall (1913), incondicional: `lim sup sigma(n) / (n log log n) = e^γ`. A hipótese de Riemann, na forma de Robin, diz que o limite superior não é atingido depois de 5040.

Se a hipótese falha, Robin mostra que algum número colossalmente abundante `n > 5040` viola a desigualdade. Alaoglu e Erdős (1944) geram esses números por um parâmetro real `ε > 0`: `n` é colossalmente abundante quando existe `ε` tal que `sigma(n) / n^{1+ε}` é máximo. O expoente de cada primo é dado por uma fórmula fechada do tipo

```text
a_p(ε) = floor( (log(p^{1+ε} - 1) - log(p^ε - 1)) / log p ) - 1
```

O relógio deixa de ser `n = n+1` e passa a ser `ε` descendo. Cada tique muda um expoente. `sigma` avalia-se fator a fator, e a fatoração multiplica de volta a `n`. Isso é observação. A lista infinita de tiques continua um `para todo`. A vantagem é que os inteiros que não podem ser recorde foram apagados do tempo.

Um prefixo dessa lista, por maior que seja, permanece certificado. Varrer campeões até `224403121196654400` e encontrar o mais apertado em `n = 55440`, com `G / e^γ` cerca de `0.983`, não fecha o quantificador.

### 6.3 Um zero com parte real certificada

Um número de voltas de `zeta` num contorno, com majorante do erro, é um testemunho finito de um zero fora da reta crítica. A altura varrida até `T` é um prefixo do espectro. Cerca de `10^13` zeros já medidos caem na reta. O prefixo não lê os zeros que ainda não entraram na janela.

### 6.4 Uma janela da fórmula explícita de Weil

Para uma função teste `F` suave e de decaimento rápido, com transformada de Fourier `φ` e `Φ(1/2 + it) = φ(t)`, a fórmula explícita de Weil iguala uma soma sobre os zeros não triviais `ρ` a uma soma sobre as potências de primos:

```text
Φ(0) + Φ(1) - ∑_ρ Φ(ρ)
    = ∑_{p,m} (log p) / p^{m/2} ( F(log p^m) + F(-log p^m) )
      - (1 / 2π) ∫ φ(t) Ψ(t) dt
```

`Ψ` é o termo arquimediano, com a digama `Γ'/Γ`. Primos são o sinal no tempo `log p^m`. Zeros são as frequências. Uma janela de suporte `[-L, L]` usa só os primos com `log n < 2L`. A positividade de Weil em toda janela equivale à hipótese de Riemann. Uma janela é uma observação. A família de todas as janelas é de novo o `para todo`.

O critério de Weil pede `Q(f) >= 0` para toda função teste admissível. Estender a positividade de uma janela curta para todas as janelas é o mesmo problema, escrito no domínio da frequência.

### 6.5 Um real que empacota a hipótese

A função `ξ` deformada pelo calor para trás tem todos os zeros reais para tempos maiores que a constante de de Bruijn–Newman `Λ`. Rodgers e Tao (2020) provaram `Λ >= 0`. A hipótese de Riemann é a igualdade `Λ = 0`.

Cotas superiores publicadas e revisadas:

- Polymath (2019): `Λ <= 0.22`
- Platt e Trudgian, corolário publicado: `Λ <= 0.2`

Cotas mais apertadas anunciadas em 2026 circulam como preprint. Várias estão sem revisão, e algumas dependem de hipóteses externas. A observação estável é o intervalo `[0, 0.2]`. O colapso do intervalo no ponto `0` é a prova que não está escrita. Um valor `Λ > 0` certificado seria a refutação inteira, um número só, sem lista de zeros. Esse valor não foi exibido.

## 7. Oito mapas

Cada mapa abaixo é uma correspondência matemática. A analogia serve de dicionário. Ela não é o teorema.

### 7.1 A tábua e o analisador

A fórmula de Weil é unitária: o produto interno no tempo dos primos iguala o produto interno nas frequências dos zeros. Medir o mar num porto durante um intervalo finito reconstrói só as frequências que cabem na janela. O espectro completo é um objeto. A medição é um prefixo. A hipótese diz que toda frequência cai na linha `Re(s) = 1/2`. A prova seria uma razão finita pela qual nenhuma frequência sai da linha. Somar `10^13` picos alonga a janela.

O ensaio de origem chama isso de sino, tábua de marés e rio. O dicionário nomeia os dois lados: o produto de Euler (o sinal dos primos) e a equação funcional (o espelho que completa o espectro). Amplitude que cresce com `Re(ρ)` restabelece o enunciado. Não o força.

### 7.2 O calor como relógio

`Λ` é o instante em que a deformação térmica torna os zeros reais e os mantém reais. O tempo aqui já é um real, não um inteiro. Observar `Λ` é apertar um intervalo. `Λ >= 0` está provado. `Λ = 0` é a hipótese. Um instante `Λ > 0` seria a refutação inteira. Esse instante não foi exibido.

Este é o exemplo limpo de criação de número: infinitos zeros, uma constante, uma pergunta finita sobre ela.

### 7.3 Dois relógios no mesmo corpo

Cada primo dá um relógio `p`-ádico. A observação é um resíduo `mod p^k`. O inteiro `p`-ádico é a sequência infinita coerente desses resíduos. O lugar arquimediano é o relógio real, lido pelo fator gama.

O adele é o ponto que carrega todos os relógios de uma vez. O produto de Euler lê os lugares finitos, para `Re(s) > 1`:

```text
zeta(s) = ∏_p (1 - p^{-s})^{-1}
```

A função completa lê o lugar infinito e o espelho:

```text
ξ(s) = (1/2) s (s - 1) π^{-s/2} Γ(s/2) zeta(s)
ξ(s) = ξ(1 - s)
```

Um relógio só não decide.

- Só a equação funcional: Davenport–Heilbronn tem um zero em `0.808517 + 85.699348 i`, e a zeta de Epstein com número de classes maior que 1 tem zeros fora da reta. Há infinitos zeros na reta nesses exemplos. Infinitos na reta não forçam todos.
- Só o produto de Euler: sistemas de Beurling, e o de Diamond–Montgomery–Vorhauer, têm zeros sobre a curva `σ = 1 - a / log t`.

O número novo que decidiria a hipótese teria de ser um objeto em que os dois relógios entram numa desigualdade só. A cohomologia de Weil faz isso para variedades sobre um corpo finito, com um Frobenius geométrico e pesos puros. `Spec(Z)` não tem essa cohomologia, não tem um `q` global, e o fator gama não é um polinômio de Frobenius. O adele já existe. O emparelhamento que o torna positivo, e que morre em Davenport–Heilbronn, não está construído.

### 7.4 A série que congela todos os pares

```text
(∑_p x^p)^2 = ∑_n r_2(n) x^n
```

Um objeto. Cada par `n` é um coeficiente. O emparelhamento dos expoentes é a involução `ι_n(k) = n - k`. Goldbach binário é `r_2(n) > 0` para todo par `n >= 4`.

Expandir até o grau `N` é olhar o relógio até `N`. Uma identidade que force todos esses coeficientes positivos apagaria o relógio. Essa identidade não está escrita.

No círculo, o mesmo objeto é

```text
r(n) = ∫_0^1 S(α)^2 e^{-2π i n α} dα
S(α) = ∑_{p <= n} e^{2π i p α}
```

Os arcos maiores carregam a série singular, produto local de Euler. Os arcos menores são a obstrução. O colapso seria uma comparação estrutural entre os dois, para todo par fora de um conjunto excepcional finito. `S(α)^3` é o gerador do Goldbach fraco, que é teorema. O quadrado permanece aberto.

A forma bilinear `∑_{k=1}^{n-1} Λ(k) Λ(n - k)` é o mesmo emparelhamento escrito com a função de von Mangoldt. Ela vê potências de primos. Lê-la como Goldbach binário troca o enunciado.

### 7.5 O relógio dos recordes

`ε` desce, e o número colossalmente abundante muda só quando um expoente de primo muda. O tempo `n = 1, 2, 3, …` é substituído por uma sequência esparsa, definida por fórmula. Se a hipótese é falsa, algum tique desse relógio fica com `G(n) >= e^γ`. Percorrer os tiques ainda é infinito. Os tiques que não podem ser recorde foram apagados.

Nicolas (1983) faz o análogo no outro extremo: a hipótese equivale a `N_k / φ(N_k) > e^γ log log N_k` para todo primorial `N_k = 2 · 3 · … · p_k`. O relógio é o índice `k` do primorial, não o inteiro genérico. Um primorial que falhe é uma refutação. Um prefixo de primoriais é um certificado.

Li (1997) dá outro relógio enumerável: `λ_n >= 0` para todo `n >= 1`, com `λ_n` extraído de `log ξ` em `s = 1`, equivalente a uma soma sobre os zeros. Um `λ_n < 0` com cauda certificada refuta. Os primeiros coeficientes positivos não provam.

### 7.6 A lâmpada, em forma correta

Infinitos passos dentro de um tempo finito têm limite. O limite de "ainda não apareceu contraexemplo" não é o certificado "não existe contraexemplo". A informação parcial passa ao limite como número quando existe módulo de convergência, como numa sequência de Cauchy. `Λ` tem módulo: as cotas publicadas. A desigualdade de Robin, percorrida em `n`, não tem módulo de convergência escrito. Por isso a lista de checagens não cola num real que se possa apertar até um ponto.

### 7.7 O ordinal como duração

`ε₀` é um número. Nomeá-lo cabe numa linha. Indução até `ε₀` prova a consistência da aritmética, coisa que nenhuma indução finita interna à aritmética prova. O passo infinito virou um nome finito, e o nome carrega força lógica.

O análogo procurado é um ordinal, um operador ou uma série cujo nome finito arraste o `para todo` da hipótese ou de Goldbach.

Hilbert–Pólya pede um operador autoadjunto cujos autovalores sejam as ordenadas dos zeros. Autoadjunção implica espectro real, e espectro real nessas ordenadas é a hipótese. O operador diagonal construído a partir dos próprios zeros tem espectro real exatamente quando a hipótese é verdadeira. Esse objeto repete a pergunta. O operador que serviria nasce dos primos e da fórmula de Poisson, e a autoadjunção é um teorema independente do lugar dos zeros. Esse operador não está construído.

### 7.8 O sítio em que o tempo já foi apagado

Números figurados são o lugar clássico em que uma soma infinita em `n` é um polinômio.

O número `k`-gonal:

```text
P(j, k) = j * ((k - 2) j - (k - 4)) / 2
```

A pirâmide `k`-gonal é a soma das primeiras `n` camadas:

```text
Pyr(n, k) = n (n + 1) ((k - 2) n + (5 - k)) / 6
```

A recorrência acumula `P(j, k)`. Os dois lados são polinômios. Coincidir em `grau + 1` pontos cola todos os instantes num valor fechado. O tempo `n` é eliminado.

O prisma `k`-gonal é cúbico:

```text
Pr(n, k) = n * ((2k - 7) n^2 - (2k - 7) n + 2) / 2
```

O simplex de dimensão `d` é o binômio `C(n + d - 1, d)`, e a identidade do taco de hóquei escreve esse binômio como soma de binômios de dimensão `d - 1`. De novo uma soma sequencial colada numa forma fechada.

Esse é o formato da prova que se procura:

```text
para todo n, Rec(n) = Closed(n)
        equivale a uma identidade, uma positividade, ou uma cobertura finita
        equivale ao enunciado aberto
```

Nas figuradas, a primeira equivalência é teorema de combinatória finita. Em Robin, a equivalência seria `G(n) < e^γ` para todo campeão gerado por `a_p(ε)`. Em Goldbach, seria `r_2(n) > 0` para toda classe de uma cobertura finita da involução `ι_n`. Em Li, seria `λ_n >= 0` a partir de `log ξ`. Em de Bruijn–Newman, seria `Λ = 0`.

O formato, nas figuradas, está preenchido. Nos dois problemas abertos, o lugar do número está nomeado, e o colapso desse número no enunciado não está provado.

## 8. O mapa

```text
tempo potencial     n = 0, 1, 2, ...
                    observa um n
                    refuta se algum n falha
                    não prova se nenhum falhou até agora
        |
        v
relógio reparametrizado
                    campeões por ε
                    primoriais de Nicolas
                    janela de Weil de largura L
                    máquina de Turing
                    menos instantes, a mesma assimetria
        |
        v
número completo
                    real, p-ádico, série, adele, Λ, ordinal
                    uma pergunta finita sobre o número
        |
        v
prova ou refutação
                    texto finito
                    Λ = 0, ou Λ > 0
                    todo coeficiente par positivo, ou um coeficiente zero
                    emparelhamento de Weil >= 0 em toda janela,
                    ou uma janela com energia negativa
                    um campeão acima do envelope, ou a desigualdade em todos
```

## 9. O que isto não fecha

Tempo infinito, no relógio potencial, refuta uma sentença `Π⁰₁` falsa. Só isso. A criação de número é o gesto que transforma a sequência numa pergunta finita. A observação continua sendo intervalo, coeficiente, resíduo, contorno ou produto de primos.

Falta o objeto `F` que ligue os dois lados ao quantificador inteiro.

- Para a hipótese de Riemann: o emparelhamento positivo alimentado pelo produto de Euler e por `ξ(s) = ξ(1 - s)`, que morre em Davenport–Heilbronn e em Beurling, ou o colapso `Λ = 0`, ou a desigualdade de Robin em todo campeão.
- Para Goldbach binário: uma cobertura finita da involução `ι_n`, ou uma identidade dos coeficientes de `(∑_p x^p)^2`.

Enquanto `F` não existe, o catálogo de identidades organiza a forma do colapso e recusa três atalhos: o varrido apresentado como prova, a repetição de um equivalente já conhecido apresentada como avanço, e a transferência de um teorema de outra geometria para `zeta`.

A hipótese de Riemann permanece aberta. Goldbach binário permanece aberto.

## Fontes

- Lagarias, J. C. *An elementary problem equivalent to the Riemann hypothesis.* American Mathematical Monthly 109 (2002). Problema E, `sigma(n)` e `H_n`.
- Robin, G. *Grandes valeurs de la fonction somme des diviseurs et hypothèse de Riemann.* J. Math. Pures Appl. 63 (1984). O equivalente para `n > 5040`.
- Gronwall, T. H. (1913). `lim sup sigma(n)/(n log log n) = e^γ`, incondicional.
- Alaoglu, L.; Erdős, P. (1944). Números superabundantes e colossalmente abundantes. O relógio `ε`.
- Nicolas, J.-L. *Petites valeurs de la fonction d'Euler.* J. Number Theory 17 (1983). Primoriais.
- Li, X.-J. *The positivity of a sequence of numbers and the Riemann hypothesis.* J. Number Theory 65 (1997).
- Weil, A. Fórmula explícita. Primos no tempo, zeros na frequência.
- Rodgers, B.; Tao, T. *The de Bruijn–Newman constant is non-negative.* Forum of Mathematics, Pi (2020). `Λ >= 0`.
- Polymath. Cota publicada `Λ <= 0.22` (2019). Platt e Trudgian, corolário `Λ <= 0.2`.
- Kreisel. A hipótese de Riemann como sentença `Π⁰₁`. Turing a tinha em `Π⁰₂`.
- Dorais, F. G., e respostas em *Is the Riemann Hypothesis equivalent to a Π₁ sentence?* MathOverflow 31846.
- *Can the Riemann hypothesis be undecidable?* MathOverflow 79685. Falsidade implica refutação provável. Verdade sem prova em ZFC permanece possível.
- Aaronson, S.; Yedidia, A. (2016). Máquinas de 5372, 4888 e 7918 estados. Aaronson, *The Busy Beaver Frontier*, máquina de 744 estados.
- Matiyasevich, Yu. Máquina de registradores equivalente à hipótese, a partir da forma `Π⁰₁`.
- Overspill. O conjunto dos inteiros padrão não é interno. Uma propriedade de primeira ordem verdadeira em todo padrão vale em algum hipernatural.
- Gentzen, G. Consistência da aritmética por indução até `ε₀`.
- Davenport, H.; Heilbronn, H. (1936). Zero fora da reta com equação funcional e sem produto de Euler. Testemunha `0.808517 + 85.699348 i` (Spira; Balanzario–Sánchez-Ortiz).
- Diamond, H. G.; Montgomery, H. L.; Vorhauer, U. M. A. *Beurling primes with large oscillation.* Math. Ann. 334 (2006).
- Helfgott, H. A. Goldbach fraco. Teorema sobre ímpares, não sobre o quadrado binário.
- Shunia, J. M. arXiv:2609.30306 (2026). Máquina de 120 estados. Preprint, à espera de auditoria ponta a ponta.
- Broughan, K. arXiv:2312.11565 (2024). Afirmação de decidibilidade em PA. Mais forte que o consenso citado acima. Não é o enunciado usado neste texto.
