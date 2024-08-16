# Web Scraping de Dados de Processos Judiciais - Projeto

Este projeto tem como objetivo extrair dados de movimentações de processos judiciais do site do Tribunal de Justiça de São Paulo (TJSP) usando o Selenium WebDriver. O script coleta informações sobre movimentações processuais a partir de um número único de processo (NUP) fornecido e organiza esses dados em um DataFrame do Pandas para análise posterior.

# Requisitos

Antes de executar o projeto, verifique se você tem os seguintes requisitos instalados:

- Python 3.8 ou superior
- Pandas: Biblioteca para manipulação e análise de dados.
- Selenium: Biblioteca para automação de navegadores.
- WebDriver: Driver do navegador Chrome (chromedriver) compatível com a versão do navegador.

# Configuração do WebDriver

Certifique-se de baixar o WebDriver do Chrome (chromedriver) da página oficial e coloque o caminho do executável do chromedriver na variável service no código.

# Uso

Para usar o script, defina a variável nup com o número do processo desejado e execute a função buscar_dados_processo_incremental(nup).

# Exemplo de uso

![image](https://github.com/user-attachments/assets/6a8c4b6c-b383-40b5-9caf-47485afe4e8f)

# Função buscar_dados_processo_incremental(nup)

Parâmetros
- nup (str): Número único do processo, que deve ter o formato '1234567-89.2021.8.26.1234'.

Retorno
DataFrame: Um DataFrame do Pandas contendo as seguintes colunas:

- Data Movimentação: Data da movimentação processual.
- Título: Título da movimentação.
- Descrição Detalhes: Detalhes adicionais da movimentação.
- Documento: Indicador se há um documento vinculado (Sim/Não).

# Funcionamento

- Inicialização: Configura o WebDriver e acessa a página de consulta do TJSP.
- Entrada de Dados: Preenche os campos obrigatórios do formulário com o número do processo e o código do foro.
- Submissão e Navegação: Submete o formulário e navega para a seção de movimentações.
- Extração de Dados: Coleta e processa as movimentações do processo, ignorando a última movimentação registrada.
- Criação do DataFrame: Organiza os dados em um DataFrame do Pandas.

# Observações

O código 'crawler_esajsp_incremental' utiliza a abordagem incremental, ou seja, ele busca apenas movimentações novas com base em uma data alvo (target_date).
O código 'crawler_esajsp' busca todas as movimentações.
Verifique a compatibilidade entre o WebDriver e a versão do navegador Chrome instalado.


