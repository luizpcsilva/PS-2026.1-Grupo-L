# 🚌 Frota Fácil RJ - UFRJ Analytica (PS 2026)

**Autores:** Luiz Paulo Corrêa da Silva & João Vitor Pereira  
**Equipe:** Grupo L  

---

## 📖 Panorama Geral do Projeto

O **Frota Fácil RJ** é uma Ferramenta de Apoio à Tomada de Decisão focada em resolver um dos maiores problemas de mobilidade urbana do Rio de Janeiro: a imprevisibilidade do tempo de ciclo das linhas de ônibus devido os engarrafamentos.

As concessionárias de transporte público são obrigadas contratualmente pela Prefeitura a cumprir intervalos mínimos de partida (o *headway*), estipulados via diretrizes GTFS. No entanto, o trânsito caótico afeta diretamente o tempo de ciclo de cada linha. Sem ferramentas preditivas, dimensionar a frota necessária torna-se um palpite, gerando multas, custos operacionais excessivos e longas esperas para os passageiros.

Nós ensinamos o comportamento da duração das viagens de ônibus a uma Inteligência Artificial. Cruzamos a base de GPS da Zirix com as regras da Prefeitura e criamos um modelo de **Machine Learning (Random Forest)** que prevê o **tempo de ciclo exato** de qualquer linha, em qualquer horário e dia. 

Com a predição correta, o sistema aplica a fórmula de dimensionamento dinâmico da frota ($F = T / H$), permitindo que as empresas ajustem a quantidade de veículos nas ruas minuto a minuto.

### 🚀 Nossos Resultados
* **Precisão (R²):** 86%
* **Margem de Erro (MAE):** ~7 Minutos
* O modelo converteu o caos em previsibilidade estocástica, trazendo uma otimização de frotas baseada em dados em tempo real.

---

## 📂 Estrutura do Repositório (Notebooks)

Para facilitar a leitura e execução, a lógica principal do projeto foi dividida em 3 arquivos Google Colab distintos. Abaixo está a função de cada um deles:

### 1️⃣ `Coleta EDA e Processamento de_dados PS.2026 Grupo L.ipynb`
Neste notebook, realizamos a importação das bases de dados (GTFS e Zirix), a Análise Exploratória de Dados (EDA) e a limpeza inicial. É aqui que lidamos com valores nulos, filtramos ruídos físicos (ex: remoção de outliers de velocidade fora do limite de 5 a 65 km/h) e realizamos o cruzamento de tabelas. 

### 2️⃣ `Treinamento do Modelo PS.2026 Grupo L.ipynb`
Este notebook é dedicado exclusivamente à construção do modelo preditivo da aplicação. Utilizamos os dados previamente limpos para treinar o nosso modelo preditivo baseado em **Random Forest**. É aqui que o modelo aprende os padrões de trânsito em diferentes horários de pico e dias da semana.

### 3️⃣ `Visualização dos dados PS.2026 Grupo L.ipynb`
Notebook focado em demonstrar o comportamento do modelo e extrair *insights* de negócio. Nele, geramos o cálculo de dimensionamento da frota e gráficos, apresentando a variação do tamanho da frota no decorrer do dia.

---

## 🗄️ Acesso aos Dados

Para executar as células dos notebooks (`.ipynb`), é necessário ter acesso às bases de dados brutos e tratadas do projeto. 

⚠️ **Atenção:** O link direto para a pasta do Google Drive contendo os dados necessários (`DadosAnalyticaPS2026-GrupoL`) encontra-se no arquivo **`Observações.pdf`**, que foi anexado junto à entrega do projeto. Por favor, consulte este arquivo para obter o link de acesso e as instruções de mapeamento de diretório antes de rodar os Colabs.

---

*Projeto desenvolvido para o Processo Seletivo da UFRJ Analytica 2026.*
