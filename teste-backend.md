# Desafio para Engenheiro de Software - VAGAS.com

Este documento descreve o exercício de programação para a vaga de Engenheiro de Software da VAGAS.com.

## Considerações sobre o desafio

* O prazo para entrega da solução é de 7 dias corridos contados a partir da data de recebimento do desafio. Caso você precise de mais tempo entre em contato conosco e fechamos uma nova data para a entrega. Não se preocupe, somos super flexíveis ;)
* Você pode utilizar qualquer linguagem de programação de propósito geral (https://en.wikipedia.org/wiki/General-purpose_programming_language) e frameworks necessários para a implementação da solução
* O código produzido deve estar versionado em algum repositório público (de preferência Github)
* Você deve mandar e-mail para codesubmissions@vagas.com.br com o assunto `Engenheiro de Software VAGAS.com - <%SEU_NOME%>` e o link para o seu repositório.

## Moradores da Terra (FIXME: Ver com Marketing)

Elaboramos alguns dados para que você utilize na sua solução. Neste [arquivo](terra.json) você encontrará mil moradores da Terra e seus atributos. A estrutura do arquivo e de cada um dos moradores é a seguinte:

```javascript
{
  "id": 1,
  "nome": "José da Silva",
  "habilidades": ["inteligente", "carisma", "forte"],
  "data_nascimento": 1990-01-01
}
```

Estes dados devem ser utilizados para a execução do exercício descrito abaixo. Sugerimos deixar todos os dados em memória durante a execução da solução, mas você pode utilizar um banco de dados para facilitar a sua implementação.

## Desafio

Com o objetivo de organizar os moradores da Terra, queremos que você crie uma API REST para nos ajudar nesta difícil empreitada. A sua API proverá as seguintes funções:

### 1. Crie um morador na Terra (FIXME: Ver com Marketing)

Este endpoint será responsável por adicionar mais um morador ao grupo existente. Os atributos obrigatórios devem ser preenchidos e seus valores devem estar de acordo com o limite de cada um. Abaixo mostramos o comportamento esperado para esta função:

Request:
```
POST /moradores
```

Body:

```json
{
  "nome": "João de Souza",
  "habilidades": ["veloz", "perseverante"],
  "data_nascimento": 1990-01-02
}
```

Validações a serem feitas:

* Nome tem que ter um mínimo de 3 caracteres e máximo de 50 caracteres
* Idade deve ser de no mínimo 18 anos
* Todo morador deve ter pelo menos uma habilidade

Response:

O response para esta função será definido por você e faz parte da avaliação.

### 2. Busque um morador por id (FIXME: Ver com Marketing)

Este endpoint será responsável por buscar um morador específico no grupo existente a partir de seu `id`. Abaixo mostramos o comportamento esperado para esta função:

Request:
```
  GET /moradores/{id}
```

Response:

```json
{
  "id": 1,
  "nome": "José da Silva",
  "habilidades": ["inteligência", "carisma", "força física"],
  "idade": 28
}
```

### 3. Encontre moradores a partir de suas habilidades (FIXME: Ver com Marketing)

Crie um endpoint que retornará uma lista de moradores a partir de suas habilidades. Porém, desejamos que o endpoint retorne moradores com habilidades similares ao que estamos buscando. Por exemplo: ao buscarmos por 'teste', o seu endpoint retornaria candidatos com habilidades como 'testes', 'testar' e 'testador'. Estas habilidades serão tratadas como texto e a busca deverá ser feita na base existente de moradores. Esperamos que o algoritmo de busca seja feito por você sem a utilização de um framework auxiliar.

Esperamos uma lista com os moradores no formato abaixo e com um escore (definido por você) para a existência dos termos pesquisados:

Request:
```
  GET /moradores?habilidade={string}
```

Response:

```json
{
  TODO
}
```

### 4. Documentação e deploy

Crie uma documentação breve sobre a sua solução, com explicação sobre o design e hipóteses assumidas. Esperamos também um passo a passo de como executar a sua solução. Quanto mais simples for, melhor será. A utilização de Docker é um plus ;)

## Avaliação

A sua solução será avaliada por um time de engenheiros de software aqui da Vagas.com e iremos nos basear nos seguintes critérios:

### Execução

* **Execução:** Conseguimos executar a solução baseados na documentação enviada? Todos os requisitos foram implementados na solução entregue?
* **Performance:** A sua solução possui uma performance adequada? Em quais casos pode haver lentidão na resposta? Caso tenha alguma ideia, há como deixar o desempenho da solução ainda melhor?

### Código

* **Manutenibilidade e extensibilidade:** O código escrito é de fácil leitura? O quão fácil é criar novas funcionalidades na solução existente?
* **Arquitetura e Design:** Como está desenhada a solução? As responsabilidades estão bem separadas? Foi utilizada alguma técnica para guiar o desenvolvimento?
* **Qualidade:** Foi utilizada alguma ferramenta de estilo de código para a linguagem? A solução possui testes unitários? É fácil alterar os testes caso haja modificação na solução?

Esperamos que você se divirta codificando essa solução e estamos aqui (codesubmissions@vagas.com.br) caso surjam dúvidas durante o desenvolvimento. Fique à vontade para melhorar o desafio e mostrar toda a sua capacidade!

Bom código! ;)