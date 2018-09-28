
# Chamada para Desenvolvedores - Time de Scraping #

Teste prático para os desenvolvedores candidatos as vagas do time de scraping.

### Objetivo ###

Construir um crawler para alguma loja online utilizando o framework Scrapy.

O código deverá ser disponibilizado no Github assim como as instruções para replicar a execução do mesmo.

### Spider de Produto ###

A spider deve extrair informações de cada produto na página do Marketplace escolhido.
Ela deve navegar em cada categoria de produto disponível (Ex: Games / Playstation / Jogos para PS4) até o menor nível possível para extrair cada produto.

Alguns desses campos podem não estar presentes na página de produto.

Campos:

* url: (*string*) Url do produto sendo extraído
* nome: (*string*) Nome do produto
* descricao: (*string*) Texto contendo a descrição do produto
* categoria: (*string*) Categoria em que o produto se enquadra
* marca: (*string*) Marca do produto
* navegacao: (*string list*) Lista de categorias e subcategorias de navegação, indo do mais geral para mais específico
* nome_vendedor: (*string*) Nome do vendedor do produto
* valor: (*float*) Valor atual do produto
* valor_antigo: (*float*) Valor do produto sem desconto, se houver
* imagem_principal: (*string*) URL da imagem do produto
* imagens_secundarias: (*string list*) Lista de URL das imagens secundárias
* caracteristicas: (*list dict*) Lista de dicionários contendo as caracteristicas do produto
		Ex.: [{'name': 'Cor', 'value': 'Preto'}]
* dimensoes: (*dict*) Dicionário com as dimensões do produto
		Ex.: {'altura': '2,00 cm', 'largura': '40,00 cm', 'peso': '2,59 kg'}

### Avaliação ###

Demonstrar boa utilização do framework entre outras habilidades explorando os pontos abaixo:

* Utilização de `xpath` nas buscas por links (obrigatório)
* Persistência das informações (Preferencialmente PostgreSQL ou MongoDB) (obrigatório)
* Tratamento de paginação
* Manipulação de querystrings
* Utilizar logs para sinalizar ocorrências durante o scraping

Quaisquer dúvidas podem ser enviadas para arthur@intelivix.com. O candidato deve registrar o tempo despendido para o desenvolvimento. Não existe um escopo de tempo oficial, mas o ideal é que não ultrapasse 1 semana.
