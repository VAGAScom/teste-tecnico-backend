# Processo Seletivo Vagas

## Engenheiro de Software

Um recrutador precisa analisar as candidaturas recebidas para vagas de emprego. Dado o grande volume de candidaturas em algumas vagas, olhar um-a-um seria um trabalho muito demorado.

Seu papel aqui é ajudar o recrutador, indicando para cada vaga as pessoas mais aderentes. Para isso, crie uma API de acordo com as especificações a seguir.

Acreditamos que a estrutura a seguir é adequada para a solução do problema, porém sinta-se a vontade para adicionar o que achar necessário.

### Especificações da API

Considerações gerais:

* **Níveis de experiência**:
  * **1**: estagiário
  * **2**: júnior
  * **3**: pleno
  * **4**: sênior
  * **5**: especialista
* **Localidades**: representadas por letras do alfabeto. Verificar no mapa abaixo os caminhos e distâncias entre as localidades

![](./graph.png)



#### 1. Criar um endpoint para cadastrar vagas de emprego

**POST:** `http://localhost:9000/v1/vaga`

**Body:**

```json
{
    "empresa": "Teste",
    "titulo": "Vaga teste",
    "descricao": "Criar os mais diferentes tipos de teste",
    "localizacao": "A",
    "nivel": 3
}
```



#### 2. Criar um endpoint para cadastrar pessoas

**POST:** `http://localhost:9000/v1/pessoa`

**Body:**

```json
{
    "nome": "John Doe",
    "profissao": "Engenheiro de Software",
    "localizacao": "C",
    "nivel": 2
}
```



#### 3. Registrar candidatura de uma pessoa em uma vaga

Neste endpoint, além de registar a candidatura, deverá também ser calculado o **score***  do candidato para a vaga em questão.

**POST:** `http://localhost:9000/v1/candidatura`

**Body:**

```json
{
    "id_vaga": 1,
    "id_pessoa": 2
}
```

##### Cálculo do score:

$$ SCORE = N + 3 \times D$$, onde:

* $$N =  100 - 25 \times |n_v - n_c|$$, onde:
  * $n_v$ é o nível da vaga
  * $$n_c$$ é o nível do candidato
* $$D = \dfrac{1}{d_{menor}} \times 100$$, onde $$d_{menor}$$:
  * $$1$$, se a vaga e o candidato estão na mesma localidade
  * ***Menor distância entre o candidato e a vaga***, caso contrário


Considere somente a parte inteira do *SCORE*.

*_Esperamos que você implemente o algoritmo do cálculo da distância, porém sinta-se a vontade para estudar e utilizar algoritmos conhecidos_

*_Ressaltando que esta é uma fórmula hipotética_



**Exemplo de cálculo**

Considere um candidato de nível Pleno (3), que mora na localidade B, que candidatou-se para uma vaga em uma empresa na localidade E. A vaga em questão é para um cargo de nível Sênior (4).

O cálculo do score, ficaria da seguinte maneira:

- _Calculando a distância (D) entre o candidato e a empresa:_

  - D = 1/dmenor x 100
  - D = 1/11 x 100
  - D = 9,09

- _Calculando o nível (N):_

  - N = 100 - 25 X |nv - nc|
  - N = 100 - 25 X |4 - 3|
  - N = 100 - 25 X 1
  - N = 100 - 25
  - N = 75

- _Cálculo do SCORE final:_

  - SCORE = N + 3 X D

  - SCORE = 75 + 3 X 9,09

  - SCORE = 75 + 27,27

  - SCORE = 102,27

  - SCORE = 102

    ​

#### 4. Criar um endpoint para retornar os candidatos de uma vaga, ordenados pelo score

**GET:** `http://localhost:9000/v1/vaga/1/candidaturas/ranking`

**Response:**

```json
[
    {
        "nome": "Mary Jane",
        "profissao": "Engenheira de Software",
        "localizacao": "A",
        "nivel": 4,
        "score": 375
	},
    {
        "nome": "John Doe",
        "profissao": "Engenheiro de Software",
        "localizacao": "C",
        "nivel": 2,
        "score": 100
	},
    ...
]
```

