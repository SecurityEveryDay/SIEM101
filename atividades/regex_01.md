## 📝 Texto para os exercícios de Regex

Use o texto abaixo **como está**, copiando para o editor de regex:

```text
Goku sempre foi conhecido como um guerreiro de coração puro, mesmo sendo um Saiyajin enviado originalmente à Terra como bebê. 
Com o tempo, ele formou uma família com Chi-Chi e passou a treinar seu filho Gohan para que também pudesse se defender em um universo cheio de perigos.

Quando Raditz chegou à Terra, revelou a verdadeira origem de Goku e tentou convencê-lo a destruir o planeta. 
Essa tentativa falhou graças à união de Goku e Piccolo, que lutaram juntos pela primeira vez. 
Embora o preço da vitória tenha sido alto, essa batalha abriu caminho para desafios ainda maiores.

Depois, a chegada de Vegeta e Nappa colocou os Guerreiros Z à prova. 
Mesmo com perdas dolorosas, como a morte de alguns amigos, o grupo continuou treinando. 
Vegeta ajustou seu Scouter várias vezes para medir o poder de luta de Goku e dos outros Guerreiros Z, surpreso com o crescimento constante de todos.
A ideia de superar limites se tornou quase uma regra: lutar, cair, aprender e levantar de novo.

Na Capsule Corp, Bulma configurou um servidor com nome de host capsulecorp.local e criou o usuário goku.ssj para que Goku pudesse acessar os relatórios de batalha remotamente. 
O acesso era feito a partir do IP 192.168.0.42, e os relatórios mais importantes eram enviados por e-mail para o endereço guerreiro.z@capsulecorp.com, que era lido por toda a equipe dos Guerreiros Z.

A viagem até Namekusei mudou completamente o rumo da história. 
Lá, em busca das esferas do dragão, os heróis encontraram o tirano Freeza, um inimigo capaz de destruir planetas sem esforço. 
Durante essa saga, Goku alcançou pela primeira vez a forma de Super Saiyajin, movido pela raiva e pelo desejo de proteger seus amigos.

Mais tarde, a aparição de Trunks do Futuro trouxe um aviso sombrio: Androides ainda mais poderosos estavam a caminho. 
Esse alerta fez com que Goku, Vegeta e os demais mergulhassem em treinos intensos, alguns dentro da Sala do Tempo, onde um dia lá dentro equivalia a um ano de treinamento.

Nem só de força física vive Dragon Ball Z. 
A relação entre Goku e Vegeta mistura rivalidade e respeito; entre Gohan e seus mestres, como Piccolo, há confiança e aprendizado. 
Em vários momentos, a amizade vence o medo, e a esperança fala mais alto que o desespero.

Em um torneio de artes marciais, Goku fez um teste curioso: escreveu em um papel "luta luta" apenas para brincar com os amigos. 
Também comentou que já gastou mais de $1000 em roupas de treino e equipamentos ao longo da vida. 
No fim do dia, após mais um treinamento pesado, ele apenas sorriu e disse: "Treino concluído OK".
```

---

## 📌 Exercícios de Regex (combinando metacaracteres)

Cada exercício deve ser resolvido **criando uma regex** que funcione sobre o texto acima.
Use apenas os metacaracteres mostrados nas tabelas: `. [] [^ ] ? * + {n,m} ^ $ \b \$ | (...) \1` e as sequências `\d \D \w \W \s \S \b \B \n \t \r`.

---

### 1. Ponto – `.` + Chaves – `{n,m}` + Borda – `\b`

Crie uma regex que encontre palavras que começam com `Go` e tenham **entre 4 e 5 letras** (como “Goku” e “Gohan”), usando o ponto como coringa, chaves para a quantidade e bordas de palavra.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\bGo.{2,3}\b
```

</details>

---

### 2. Lista – `[ABC]` + Palavra – `\w` + Quantificador – `+`

Crie uma regex que encontre todas as palavras do texto que **começam com as letras G, P ou V** (por exemplo, Goku, Gohan, Piccolo, Vegeta), usando uma lista de caracteres, `\w` e `+` para pegar o restante da palavra.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\b[GPV]\w+\b
```

</details>

---

### 3. Lista negada – `[^ABC]` + Quantificador – `*` + Palavra – `\w`

Crie uma regex que encontre todas as palavras que começam com `S` e cuja **segunda letra não é vogal** (ou seja, não é `a`, `e`, `i`, `o` ou `u`), usando uma lista negada e completando com o restante da palavra.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\bS[^aeiouAEIOU]\w*\b
```

</details>

---

### 4. Opcional – `?` + Borda – `\b`

No texto aparecem as palavras “Saiyajin” e, se você quiser, pode acrescentar manualmente “Saiyajins”.
Crie uma regex que case **tanto o singular quanto o plural**, usando um trecho opcional e bordas de palavra.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\bSaiyajins?\b
```

</details>

---

### 5. Asterisco – `*` + Espaço – `\s` + Âncora de linha – `^`

Crie uma regex que encontre linhas que possam ter **zero ou mais espaços no início** antes da palavra `Goku`, combinando `^`, `\s*` e a palavra.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
^\s*Goku
```

</details>

---

### 6. Mais – `+` + Dígito – `\d` + Borda – `\b`

Crie uma regex que encontre todas as sequências de **um ou mais dígitos** no texto (por exemplo, `1000`, `192`, `42`), usando `\d+` e bordas de palavra.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\b\d+\b
```

</details>

---

### 7. Chaves – `{n,m}` + Grupo – `(...)` + Dígitos – `\d` + Ponto – `.`

Crie uma regex que encontre o **endereço IP** presente no texto (formato IPv4), usando grupos, chaves e dígitos.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b
```

</details>

---

### 8. Circunflexo – `^` + OU – `|` + Grupo – `(...)`

Considerando cada linha como uma unidade, crie uma regex que encontre todas as linhas que **começam** com a palavra “Goku” ou “Quando”, combinando âncora de início de linha com grupo e `|`.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
^(Goku|Quando)
```

> Lembre de ativar o *multiline* (`m`) no motor de regex.

</details>

---

### 9. Cifrão – `$` + Borda – `\b` + Ponto – `.` + Opcional – `?`

Crie uma regex que encontre a **última palavra do texto** (no caso, `OK`, que aparece antes das aspas e do ponto final), usando borda de palavra e âncora de fim de linha.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\b\w+\b"?\.$
```

</details>

---

### 10. Borda de palavra – `\b` + OU – `|`

Crie uma regex que encontre a palavra **“Freeza” apenas quando ela aparecer inteira**, e, além disso, também aceite “Guerreiros” quando aparecer como palavra isolada, usando bordas de palavra e alternância.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\b(Freeza|Guerreiros)\b
```

</details>

---

### 11. Escape – `\$` + Dígito – `\d` + Quantificador – `+`

No texto há um valor monetário com o símbolo `$`.
Crie uma regex que encontre todos os valores que começam com o caractere `$` seguido de **um ou mais dígitos**, usando o escape com `\$`, `\d` e `+`.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\$\d+
```

</details>

---

### 12. OU – `|` + Grupo – `(...)` + Borda – `\b`

Crie uma regex que encontre **qualquer ocorrência** de “Goku”, “Vegeta” ou “Gohan” no texto, garantindo que sejam palavras completas, usando grupo, alternância e borda de palavra.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\b(Goku|Vegeta|Gohan)\b
```

</details>

---

### 13. Grupo – `(...)` + Espaço em branco – `\s+`

Crie uma regex que coloque em **grupos de captura** o nome e a expressão em “Trunks do Futuro”, capturando separadamente:

* o nome “Trunks”
* a expressão “do Futuro”

Use parênteses para delimitar grupos e `\s+` para o espaço entre eles.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
(Trunks)\s+(do Futuro)
```

</details>

---

### 14. Retrovisor – `\1` + Grupo – `(...)` + Espaço – `\s+` + Borda – `\b`

No texto há a expressão “luta luta”.
Crie uma regex que encontre **qualquer palavra repetida duas vezes seguidas**, como “luta luta”, usando:

* um grupo para capturar a primeira palavra;
* um retrovisor (`\1`) para casar a repetição;
* `\s+` para o espaço entre elas.

<details><summary>Resposta</summary>

**Resposta (regex):**

```regex
\b(\w+)\s+\1\b
```

</details>

---
