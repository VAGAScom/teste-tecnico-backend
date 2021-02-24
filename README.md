# teste-tecnico-backend

Repositório com todos os arquivos necessários para implementação do teste técnico da VAGAS.com.

Por enquanto, estamos apenas revisando o teste técnico de Backend, mas esperamos que o teste técnico de Frontend venha pra cá em breve.

[Engenheiro de Software](instrucoes.md)

[Desafio Técnico](desafio-tecnico.md)

## Gerando arquivos em PDF

Para gerar os arquivos rode:

```bash
# desafio-tecnico.md
docker run -v $PWD:/opt/docs auchida/markdown-pdf markdown-pdf -o desafio-tecnico.pdf desafio-tecnico.md

# instrucoes.md
docker run -v $PWD:/opt/docs auchida/markdown-pdf markdown-pdf -o instrucoes.pdf instrucoes.md
```
