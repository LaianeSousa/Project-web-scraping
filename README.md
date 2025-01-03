# Web Scraper com Selenium e Pandas

Este projeto consiste em um script Python que utiliza Selenium, BeautifulSoup, e Pandas para extrair dados de uma página da web, formatá-los como um DataFrame, e processá-los. O exemplo específico se conecta ao site Betway para coletar informações sobre times e suas probabilidades de aposta em partidas de futebol.

## Funcionalidades

- **Automação com Selenium**: Utiliza Selenium para controlar o navegador e acessar o site.
- **Extração de Dados**: Utiliza o pacote `a_selenium2df` para transformar os elementos HTML em DataFrames do Pandas.
- **Análise de HTML com BeautifulSoup**: Processa os dados HTML para extrair informações específicas, como nomes dos times e probabilidades.
- **Manipulação de Dados com Pandas**: Organiza os dados extraídos em um formato tabular para análise e uso posterior.

## Requisitos

Para executar este script, você precisará dos seguintes pacotes Python instalados:

- `seleniumbase`
- `beautifulsoup4`
- `pandas`
- `a_selenium2df`
- `PrettyColorPrinter`

Além disso, é necessário ter o WebDriver apropriado instalado para o navegador que você está utilizando (o script usa o argumento `uc=True` para evitar bloqueios em navegadores modernos).

## Instalação

1. Clone este repositório:

```bash
$ git clone <URL-do-repositorio>
```

2. Instale os pacotes requeridos:

```bash
$ pip install seleniumbase beautifulsoup4 pandas PrettyColorPrinter
```

3. Certifique-se de ter o WebDriver instalado e configurado no PATH do sistema.

## Como Usar

1. **Configuração Inicial**:
   - O script está configurado para acessar o site `https://betway.com/pt/sports/grp/socc...`. Altere o URL caso deseje acessar outra página.

2. **Execução do Script**:
   - Execute o script em um terminal ou IDE Python:

```bash
$ python nome_do_script.py
```

3. **Saída dos Dados**:
   - O script coleta informações sobre times de futebol e suas respectivas probabilidades de aposta (odds) e organiza essas informações em um DataFrame do Pandas.

   - As colunas geradas no DataFrame incluem:
     - `team1_nome`: Nome do primeiro time.
     - `team2_nome`: Nome do segundo time.
     - `team1`: Probabilidade de vitória do primeiro time.
     - `empate`: Probabilidade de empate.
     - `team2`: Probabilidade de vitória do segundo time.

## Estrutura do Código

1. **Função `obter_dataframe`**:
   - Extrai elementos HTML da página e os transforma em um DataFrame do Pandas usando `a_selenium2df`.

2. **Uso do Selenium**:
   - Configura o driver do navegador para acessar a página.
   - Inclui um loop `while` para garantir que os dados sejam coletados mesmo em caso de falhas temporárias.

3. **Processamento com BeautifulSoup**:
   - Extrai nomes dos times e probabilidades de aposta do HTML e os organiza em colunas do DataFrame.

## Tratamento de Erros

- O script utiliza um bloco `try-except` para capturar exceções durante a execução do loop de extração e tenta novamente após um intervalo de 2 segundos.

## Observações

- Certifique-se de que o site acessado permite scraping. Verifique os Termos de Uso do site antes de realizar qualquer operação de coleta de dados.
- O script utiliza um tempo de espera (`sleep(5)`) para permitir o carregamento da página antes da coleta dos dados. Ajuste este valor conforme necessário.

## Melhorias Futuras

- Adicionar suporte para exportação dos dados para arquivos CSV ou JSON.
- Implementar logs mais detalhados para facilitar a depuração.
- Tornar o URL e os seletores CSS configuráveis por meio de um arquivo de configuração ou argumentos da linha de comando.
- Melhorar a robustez do tratamento de erros.

## Licença

Este projeto está disponível sob a licença MIT. Consulte o arquivo `LICENSE` para mais informações.

