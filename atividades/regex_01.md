

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
A ideia de superar limites se tornou quase uma regra: lutar, cair, aprender e levantar de novo.

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

## 📌 Exercícios de Regex (um para cada metacaractere)

Cada exercício deve ser resolvido **criando uma regex** que funcione sobre o texto acima.

---

### 1. Ponto – `.`

Crie uma regex que encontre qualquer palavra que comece com `Go` e tenha **quatro letras**, como “Goku” e “Gohan”, usando o ponto para representar caracteres variando no final.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**
```regex
\bGo..\w*\b
```

</details>

---

### 2. Lista – `[ABC]`

Crie uma regex que encontre todas as palavras do texto que **começam com as letras G, P ou V** (por exemplo, Goku, Gohan, Piccolo, Vegeta), usando uma lista de caracteres entre colchetes.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\b[GPV][a-zA-Z]+\b
```
</details>
---

### 3. Lista negada – `[^ABC]`

Crie uma regex que encontre todas as **vogais que não sejam “a”** imediatamente após a letra `S` em qualquer palavra (por exemplo, em “Saiyajin”), usando uma lista negada.

<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
S[^aA]
```
</details>
---

### 4. Opcional – `?`

No texto aparecem as palavras “Saiyajin” e “Saiyajins” (se quiser, acrescente “Saiyajins” manualmente em algum ponto).
Crie uma regex que case **tanto o singular quanto o plural** com uma única expressão, usando um trecho opcional.

<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
Saiyajins?
```
</details>
---

### 5. Asterisco – `*`

Crie uma regex que encontre sequências que começam com a letra `S` seguida de **zero ou mais vogais**.
Use-a para localizar padrões como parte de “Sala”, “Super” etc.

<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
S[aeiouAEIOU]*
```
</details>
---

### 6. Mais – `+`

Crie uma regex que encontre todas as sequências de **um ou mais dígitos** no texto (por exemplo, `1000`, `1` em “um dia”).
Use o `+` para indicar “um ou mais”.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\d+
```
</details>
---

### 7. Chaves – `{n,m}`

Crie uma regex que encontre números com **exatamente 4 dígitos**, como `1000`, utilizando chaves para definir a quantidade exata de dígitos.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\b\d{4}\b
```
</details>
---

### 8. Circunflexo – `^`

Considerando cada linha como uma unidade, crie uma regex que encontre todas as linhas que **começam** com a palavra “Goku” ou “Quando”.
Use o circunflexo para indicar início de linha.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
^(Goku|Quando)
```

</details>

---

### 9. Cifrão – `$`

Crie uma regex que encontre a ultima palavra do texto:
Use o cifrão para ancorar o final da linha.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\w+.$
```
</details>
---

### 10. Borda de palavra – `\b`

Crie uma regex que encontre a palavra **“Freeza” apenas quando ela aparecer inteira**, sem pegar partes de outras palavras.
Use `\b` para garantir o limite de palavra.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\bFreeza\b
```
</details>
---

### 11. Escape – `\$`

No texto há um valor monetário com o símbolo `$`.
Crie uma regex que encontre todos os valores que começam com o caractere `$` seguido de um ou mais dígitos, usando o escape para tratar o `$` como literal.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\$\d+
```
</details>
---

### 12. OU – `|`

Crie uma regex que encontre **qualquer ocorrência** de “Goku” ou “Vegeta” ou “Gohan” no texto usando o operador de alternância (OU).
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\b(Goku|Vegeta|Gohan)\b
```
</details>
---

### 13. Grupo – `(...)`
<details> <summary>Resposta</summary>
  
Crie uma regex que coloque em **grupo de captura** o nome e o sobrenome em “Trunks do Futuro”, capturando separadamente:

* o nome “Trunks”
* a expressão “do Futuro”

Use parênteses para delimitar grupos.

**Resposta (regex):**

```regex
(Trunks)\s+(do Futuro)
```
</details>
---

### 14. Retrovisor – `\1`

No texto há a expressão “luta luta”.
Crie uma regex que encontre **qualquer palavra repetida duas vezes seguidas**, como “luta luta”, usando:

* um grupo para capturar a primeira palavra
* um retrovisor (`\1`) para casar a repetição.
<details> <summary>Resposta</summary>
  
**Resposta (regex):**

```regex
\b(\w+)\s+\1\b
```
</details>
---

