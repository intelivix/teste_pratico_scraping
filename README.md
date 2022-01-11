# Desafio Técnico - Scraping

## Descrição do problema

O Banco do Brasil está interessado em seus serviços para avaliar como estão seus processos em um sistema do Tribunal Federal da 5a Região (TRF5).

O sistema em questão permite consulta pública de processos no endereço [http://www5.trf5.jus.br/cp/](http://www5.trf5.jus.br/cp/) .

Alguns processos são de bastante interesse do BB, e já foram passados para você. Mas o BB também gostaria de descobrir se existe algum processo no sistema que eles desconhecem.

Para realizar esta tarefa, será necessária a implementação de um raspador.

## Especificação dos dados

Na página do processo, algumas informações devem ser obtidas, de acordo com a imagem a seguir:

![https://i.imgur.com/a9tj20t.png](https://i.imgur.com/a9tj20t.png)

De cima para baixo:

- Em vermelho, o `numero_processo` [*string*] (caso não haja conteúdo, este campo deve ser preenchido com o `numero_legado`) ;
- Em verde, o `numero_legado` [*string*];
- Em azul, a `data_autuacao` [*datetime.datetime*];
- Em ciano, os `envolvidos` [*list of dict*]:
    - À esquerda, o `papel` [*string*] do envolvido;
    - À direita, o `nome` [*string*] do envolvido;
- Em rosa, o `relator` [*string*] (apenas o nome é necessário)
- Em cinza, as `movimentacoes` [*list of dict*]:
    - Em cima, a `data` [datetime.datetime] da movimentação;
    - Embaixo, o `texto` [*string*] da movimentação.

## Requisitos

- O raspador deverá permitir realizar a busca por "N° do processo" para buscar os números de processos conhecidos;
- O raspador deverá permitir realizar a busca por "CNPJ" para descoberta de processos;
- Mostre uma maneira de persistir os dados (um arquivo JSON Lines ou banco de dados, por exemplo);
- Documentação (como executar o projeto, decisões de implementação, dificuldades encontradas e como foram resolvidas, etc.);
- O raspador deve ser implementado utilizando exclusivamente o framework Scrapy com Python 3;
- O projeto do raspador deve estar num repositório Git público (Github, Bitbucket, Gitlab, etc.).

## Critérios de avaliação

Os critérios de avaliação, em ordem de relevância:

1. Código legível, simples e claro;
2. Documentação;
3. Qualidade dos dados;
4. Arquitetura (forma de persistência dos arquivos, eficiência do raspador, bom uso do framework Scrapy, etc).

Algumas observações:

- Excesso de comentários no código não implica em boa documentação e prejudica a legibilidade do código. Mantenha apenas comentários absolutamente necessários;
- Se persistir os dados em um arquivo, não suba o arquivo pro repositório público, o projeto será executado durante a avaliação;
- Persistir os dados utilizando o mongoDB implicará em um bônus na avaliação.

## Argumentos

Lista de processos enviados pelo BB:

- 0015648-78.1999.4.05.0000
- 0012656-90.2012.4.05.0000
- 0043753-74.2013.4.05.0000
- 0002098-07.2011.4.05.8500
- 0460674-33.2019.4.05.0000
- 0000560-67.2017.4.05.0000

CNPJ do BB:

- 00.000.000/0001-91
