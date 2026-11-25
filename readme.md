Monitor de Notícias
Sistema de monitoramento automatizado de notícias com coleta em múltiplos portais de mídia via RSS, identificação de temas, monitoramento de menções a atores políticos e análise de sentimento utilizando Inteligência Artificial.

O projeto captura manchetes publicadas por veículos de comunicação previamente definidos, classifica o conteúdo por tema, identifica candidatos monitorados e calcula automaticamente o sentimento predominante das notícias.

Objetivo
Criar uma ferramenta capaz de:

Coletar notícias em tempo real através de feeds RSS.
Monitorar menções a nomes e grupos políticos.
Classificar notícias por tema de interesse.
Avaliar o sentimento das manchetes utilizando IA.
Medir volume de exposição na mídia.
Gerar rankings por veículo, candidato e sentimento.
Produzir indicadores de reputação e cobertura jornalística.
Funcionalidades
Coleta Automatizada
O sistema consulta periodicamente feeds RSS de diversos veículos de comunicação, incluindo:

G1
Band
CNN Brasil
Jovem Pan
SBT News
Poder360
CartaCapital
Brasil Paralelo
Gazeta do Povo
Revista Oeste
O Antagonista
Terra
CBN
The Economist
InfoMoney
InvestNews
Brazil Journal
Além de fontes especializadas do setor agropecuário:

CNA
Agro Goiás
Globo Rural
Agrolink
Presente Rural
Paraná Cooperativo
Identificação de Candidatos
O monitor identifica automaticamente citações relacionadas a:

Luiz Inácio Lula da Silva
Jair Bolsonaro
Flávio Bolsonaro
Eduardo Bolsonaro
Carlos Bolsonaro
A lógica pode ser facilmente expandida para incluir novos nomes.

Classificação por Temas
As notícias são agrupadas em categorias estratégicas:

Economia
Impostos
Segurança
STF
Eleições
Programas Sociais
Relações Exteriores
Outros
A classificação ocorre por meio de palavras-chave associadas a cada tema.

Análise de Sentimento
O sistema utiliza o modelo:

cardiffnlp/twitter-xlm-roberta-base-sentiment

para classificar cada manchete em:

POSITIVO
NEGATIVO
NEUTRO
Além da classificação, o modelo retorna um índice de confiança para cada análise.

Tecnologias Utilizadas
Python
Linguagem principal do projeto.

Pandas
Utilizado para:

Estruturação dos dados
Tratamento de tabelas
Filtros
Agrupamentos
Estatísticas
Feedparser
Responsável pela leitura dos feeds RSS e extração das publicações.

Transformers
Biblioteca da Hugging Face utilizada para execução do modelo de IA.

SentencePiece
Utilizado pelo modelo de linguagem para tokenização dos textos.

Plotly
Biblioteca destinada à construção de gráficos e dashboards interativos.

Instalação
Clonar o repositório
git clone https://github.com/SEU-USUARIO/monitor_de_noticias.git
Entrar na pasta
cd monitor_de_noticias
Instalar dependências
pip install pandas
pip install feedparser
pip install transformers
pip install sentencepiece
pip install plotly
Ou:

pip install -r requirements.txt
Fluxo de Execução
1. Captura de Notícias
O sistema acessa todos os feeds RSS cadastrados.

2. Identificação de Menções
Cada manchete é analisada para identificar os candidatos monitorados.

3. Classificação por Temas
As notícias são categorizadas por assunto.

4. Análise de Sentimento
As manchetes são classificadas automaticamente em:

Positivas
Negativas
Neutras
5. Consolidação
Os dados são armazenados em DataFrames Pandas.

6. Geração de Rankings
O sistema produz métricas como:

Total de notícias
Quantidade de menções
Sentimento predominante
Saldo positivo x negativo
Confiança média das análises
Última publicação identificada
Indicadores Gerados
Ranking de Exposição
Quantidade total de notícias por candidato.

Ranking de Sentimento
Comparação entre:

Positivas
Negativas
Neutras
Saldo de Imagem
Saldo = Notícias Positivas - Notícias Negativas
Confiança Média
Média dos scores retornados pelo modelo de IA.

Estrutura dos Dados
Campo	Descrição
fonte	Veículo de comunicação
titulo	Título da notícia
candidato	Nome identificado
tema	Categoria temática
sentimento	Positivo, Negativo ou Neutro
data	Data da publicação
confianca	Score da IA
Possíveis Evoluções
Dashboard em Power BI.
Dashboard com Streamlit.
Exportação automática para Excel.
Geração de relatórios em PDF.
Alertas por e-mail.
Monitoramento de novos candidatos.
Monitoramento de empresas, marcas e instituições.
Armazenamento em banco de dados.
Integração com APIs de notícias.
Observações
A classificação é realizada sobre os títulos das notícias. O sentimento identificado representa a interpretação do modelo de IA sobre o texto analisado e não necessariamente o posicionamento editorial do veículo.

