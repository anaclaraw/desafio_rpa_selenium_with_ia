### Projeto de Coleta e Análise de Vídeos em Alta do YouTube

Este projeto é uma aplicação desenvolvida em Python para automatizar a coleta de dados sobre vídeos em alta no YouTube, organizá-los em um arquivo Excel e, opcionalmente, realizar uma análise com inteligência artificial (IA) usando a API da Google Generative AI.

A aplicação utiliza:
- **Selenium**: Para acessar e extrair informações das páginas de vídeos do YouTube.
- **OpenPyXL**: Para manipulação de arquivos Excel.
- **Google Generative AI**: Para análise de tendências dos vídeos coletados.

---

#### **Funcionalidades**
1. **Coleta de dados de vídeos em alta**:
   - O programa acessa as páginas de categorias específicas no YouTube (como Música, Jogos e Filmes).
   - Extrai dados como título, link, visualizações, canal e data de postagem de até três vídeos por categoria.
2. **Armazenamento em Excel**:
   - Os dados coletados são organizados e salvos em um arquivo Excel.
3. **Análise com IA** (extra):
   - Gera insights e análises baseados nos títulos dos vídeos utilizando um modelo da Google Generative AI.

---

#### **Requisitos do Sistema**
- **Python 3.8 ou superior**.
- **Google Chrome**.
- **Bibliotecas Python**:
  - `selenium`
  - `openpyxl`
  - `google.generativeai`

---

#### **Configuração do Ambiente**

1. **Instale o ChromeDriver**:
   - Faça o download do [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) e configure seu caminho no código (variável `CHROMEDRIVER_PATH`).

2. **Instale as dependências Python**:
   Execute o seguinte comando para instalar as bibliotecas necessárias:
   ```bash
   pip install selenium openpyxl google-generativeai
   ```

3. **Obtenha uma API Key da Google Generative AI**:
   - Cadastre-se e obtenha uma chave de API no [Google Cloud Console](https://console.cloud.google.com/).
   - Configure sua chave na variável `GOOGLE_API_KEY` no código.

---

#### **Estrutura do Código**
1. **Configuração do WebDriver**:
   - `configure_webdriver(chromedriver_path)`: Inicializa o WebDriver com opções como maximização da janela, execução em modo headless e desativação de GPU.

2. **Coleta de Vídeos**:
   - `get_trending_videos(driver, category_url)`: Extrai título, link, visualizações, canal e data de postagem de vídeos em alta.

3. **Armazenamento em Excel**:
   - `save_to_excel(filepath, data)`: Salva os dados organizados em um arquivo Excel.

4. **Análise com IA**:
   - `generate_ai_analysis(prompt, api_key, model_name)`: Interage com o modelo da Google Generative AI para gerar insights baseados nos títulos coletados.

5. **Fluxo Principal**:
   - `main()`: Integra as etapas de configuração, coleta, armazenamento e análise.

---

#### **Como Executar**

1. Clone ou baixe o repositório para sua máquina local:
   ```bash
   git clone https://github.com/seu-repositorio/youtube-trending-analysis.git
   cd youtube-trending-analysis
   ```

2. Execute o script principal:
   ```bash
   python main.py
   ```

3. O arquivo Excel será salvo no caminho especificado na variável `OUTPUT_FILE`, e a análise da IA será exibida no terminal.

---

#### **Exemplo de Saída**

**Arquivo Excel**:
| Categoria | Título                     | Visualizações | Canal          | Data de Postagem | Link                           |
|-----------|----------------------------|---------------|----------------|------------------|--------------------------------|
| Música    | Exemplo de Título 1        | 2M views      | Canal Exemplo  | 2 dias atrás     | https://youtube.com/abc123    |
| Jogos     | Exemplo de Título 2        | 500k views    | Canal Jogos    | 1 dia atrás       | https://youtube.com/def456    |

**Análise da IA**:
```
Tendências dos vídeos em alta:
- A categoria "Música" apresenta maior popularidade com visualizações médias superiores a 1M.
- Canais de jogos têm maior diversidade temática e alta retenção de público.
- Vídeos recentes (<3 dias) dominam as listas de tendências.
```

---
