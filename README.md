# Reasoning, RAG e Arquitetura Multi-Agente (ReAct Agents)

Este projeto demonstra a construção progressiva de um sistema de Inteligência Artificial baseado no framework **Phidata** e modelos da **OpenAI**. A solução evolui desde agentes simples de pesquisa e análise financeira até uma arquitetura multi-agente com capacidade de raciocínio (Reasoning), RAG (Retrieval-Augmented Generation) com banco vetorial LanceDB e uma interface de usuário implantada via Streamlit.

## Estrutura do Projeto

O repositório é composto por scripts sequenciais que ilustram a evolução da arquitetura:

* `agente_pesquisa.py`: Criação de um agente individual focado em pesquisas na web utilizando a ferramenta DuckDuckGo.
* `agente_financeiro.py`: Criação de um agente financeiro que consulta cotações, recomendações de analistas e notícias de ativos via YFinance.
* `multi-agente.py`: Integração do agente de pesquisa e do agente financeiro em uma equipe multi-agente cooperativa.
* `agente_com_raciocinio.py`: Adição do recurso de raciocínio (Reasoning) e saídas estruturadas à equipe de agentes para responder a perguntas complexas.
* `agente_com_rag.py`: Implementação do pipeline RAG utilizando um PDF (Relatório Anual da Nvidia) indexado no banco vetorial LanceDB com embeddings da OpenAI.
* `agente_com_rag_deploy.py`: Interface web construída com Streamlit para disponibilizar o sistema multi-agente RAG de forma interativa.
* `requirements.txt`: Lista de dependências e bibliotecas necessárias para executar o projeto.

## Tecnologias Utilizadas

* **Linguagem**: Python 3.10+
* **Framework Agentic**: Phidata (`phidata`)
* **Modelos de LLM e Embeddings**: OpenAI (`gpt-4o` e `text-embedding-3-small`)
* **Banco de Dados Vetorial**: LanceDB
* **Ferramentas (Tools)**: DuckDuckGo Search, YFinance Tools
* **Interface de Usuário**: Streamlit

## Pré-requisitos

1. Python 3.10 ou superior instalado.
2. Uma chave de API da OpenAI (`OPENAI_API_KEY`).

## Configuração do Ambiente

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

### 2. Criar e ativar um ambiente virtual

No Linux/macOS:
```bash
python3 -m venv venv
source venv/bin/activate
```

No Windows:
```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Instalar as dependências

```bash
pip install -r requirements.txt
```

### 4. Configurar as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto e adicione sua chave da OpenAI:

```env
OPENAI_API_KEY=sua_chave_aqui
```

## Como Executar

Você pode executar cada etapa do projeto individualmente:

### Testar agentes individuais e multi-agente via CLI

* **Agente de Pesquisa Web:**
  ```bash
  python agente_pesquisa.py
  ```

* **Agente Financeiro:**
  ```bash
  python agente_financeiro.py
  ```

* **Time Multi-Agente Simples:**
  ```bash
  python multi-agente.py
  ```

* **Time Multi-Agente com Raciocínio (Reasoning):**
  ```bash
  python agente_com_raciocinio.py
  ```

* **Sistema com RAG e Banco Vetorial (Indexação do PDF + Consulta):**
  ```bash
  python agente_com_rag.py
  ```

### Executar a aplicação web (Streamlit)

Após ter executado a indexação inicial do banco vetorial (script `05`), inicie a aplicação web:

```bash
streamlit run agente_com_rag_deploy.py
```

Acesse o endereço local informado no terminal (geralmente `http://localhost:8501`) para interagir com o sistema via interface gráfica.

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.