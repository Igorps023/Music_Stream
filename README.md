# Projeto de BI em PySpark 

Objetivo principal é a entrega de um dashboard para área de BI utilizando processos de engenharia de dados em cloud AWS.

O notebook contempla toda a exploração e criação física dos processos necessários para um projeto de engenharia de dados básico.

Etapas:
- Análise dos dados
- Entendimento de "erros" de digitação e/ou linhas/colunas duplicadas
- Correção e conversão dos arquivos para formato Parquet e envio para outro bucket (Refined Zone)
- Criação de diagrama com as tabelas e relacionamentos existentes
- Fluxograma do processo de ingestão de dados até entrega de dashboards para a área de BI e clientes.
- Dashboards foram desenvolvidos em Power BI utilizando o conector Athena.

Itens adicionais:
- Mapeamento das fontes de dados
- Criação das camadas para ingestão e tratamento dos dados
- Exploração e entendimento das fontes de dados (número de linhas, colunas, tipo de arquivo)
- Tratamento para retirada de linhas com erros de digitação e/ou duplicadas
- Schema (tipagem das colunas)
- Criação de Novas Tabelas (Spark SQL)

# Diagrama 
Conforme o diagrama proposto, este projeto utilizará 3 tabelas
*   1 tabela fato - Todos os registros de músicas escutadas por usuário
*   1 tabela dimensão - Todos os usuários
*   1 tabela dimensão - Todas as musicas/artista
Diagrama feito no Draw.io

![Untitled](https://github.com/Igorps023/Music_Stream/assets/98396618/6d13aed3-918f-430c-9c42-b1500faf1eaf)

# Dashboard desenvolvido para a área de BI
![Untitled-1](https://github.com/Igorps023/Music_Stream/assets/98396618/b733be8d-237a-4718-ba6e-69e24dcceafe)
### Principais Pontos do Dashboard:
- Conexão realizada via Athena
- Dados históricos de streaming para o ano de 2020
- Ideia principal:
    - Apresentar o comportamento de streamings ao longo do ano de 2020, mapeando o principal gênero dos usuários.
    - Quais artistas, álbuns e data de lançamento de discos e singles apresentaram maiores resultados.
    - Fornecer um dashboard para entendimento macro das informações históricas, e futuramente desenvolver estudos específicos, de acordo com a necessidade da empresa.    
- O arquivo PBIX para edição do dashboard está diponível no GitHub.


### Principais Pontos do Notebook
### Arquivos criados e salvos em um bucket (S3) no formato Parquet 
- Endereco bkt origem: s3://bkt-musicstream-bi/Files/RawZone/
- Endereco bkt destino: s3://bkt-musicstream-bi/Files/RefinedZone/

![Untitled](https://github.com/Igorps023/Music_Stream/assets/98396618/b4dab70b-f9ae-4a0e-a336-36f49da7db1e)


### Tabelas Criadas
- music_info_unique (formato parquet)
- user_listening_history_raw (formato parquet)
- users (formato parquet)
