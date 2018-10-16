# Ideias para a extensão do código

### Relacionadas ao problema das localidades

- Incluir informação de distância máxima que o candidato aceita trabalhar. Caso a distância entre o candidato e a empresa seja maior que este valor máximo, não listar o candidato ou então aplicar alguma redução no _score_ ou impedir a candidatura.

- Pedir ao candidato que adicione nós no grafo:
   - um nó periférico (ex.: `F --> G` ) 
   - um intermediário (ex.: `C --> H --> E`)

- Pedir ao candidato para adicionar um limitador de candidatos no endpoint de retornar os candidatos de uma vaga

- Pedir para candidato adicionar a dimensão de tempo de trânsito no cálculo do score

- Adicionar lista de idiomas na vaga e no candidato para gerar o novo cálculo de score

- Adicionar lista de empresas desejados no candidato para gerar um novo cálculo de score

- Incluir um novo critério para o cálculo do score.
  1. Adicionar um campo "experiência" de texto livre a **pessoa**.
  2. Adicionar a seguinte lógica ao cálculo do score:
    ```
    Caso o campo "título" da 'vaga' esteja presente na "experiência" da 'pessoa', o 'score' do candidato para aquela vaga se mantém, caso contrário, o 'score' do candidato deve ser 0 (zero)
    ```

- Adicione sua ideia aqui!
