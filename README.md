
---

# 📚 Laboratório de Mineração de Conhecimento com Azure AI Search

Este repositório documenta o processo prático de criação de uma solução de **mineração de conhecimento** por busca avançada de documento do próprio azure chamado hotel-index encontrado em "Amostras". utilizando o **Azure AI Search** (Pesquisa de IA do Azure) e o **Azure AI Services**, com o objetivo de extrair, enriquecer e consultar informações provenientes de avaliações de clientes. A solução também inclui a persistência dos dados enriquecidos em uma **Loja de Conhecimento (Knowledge Store)** no Azure Blob Storage.

## 🔧 Objetivo

O objetivo deste laboratório é:

- Criar recursos essenciais no Azure (Azure AI Search, Azure AI Services e Armazenamento do Azure).
- Configurar um contêiner de armazenamento e carregar documentos para análise do próprio azure.
- Importar os dados usando o assistente de importação do Azure AI Search selecionando "Amostras".
- Realizar uma consulta avançada com palavras-chave específicas.
- Criar índices e indexação.

---

## 📦 Recursos do Azure Necessários

Antes de começar, você criou os seguintes recursos no Azure:

| Recursos | Finalidades |
|--------|------------|
| **Azure AI Search** | Gerencia a indexação e permite consultas avançadas sobre os dados. |
| **Azure AI Services** | Fornece habilidades cognitivas para enriquecimento dos dados (IA). |
| **Conta de Armazenamento do Azure** | Armazena documentos brutos, além de servir como base para a Loja de Conhecimento. |

---

## 🛠️ Passo a Passo

### 1. **Criar Recursos do Azure**

#### a) Azure AI Search

- Foi criado via portal do Azure.
- Nome único, nível de preços **Básico**, localização consistente com outros recursos.

#### b) Azure AI Services

- Criado com o mesmo grupo de recursos e região do Azure AI Search.
- Camada de preços **Standard S0** selecionada para suportar habilidades cognitivas.

#### c) Conta de Armazenamento do Azure

- Usado arquivos de amostras como "Hotel-index".
  
---

### 2. **Configuração do Armazenamento**

#### a) Criar Contêiner

- Um registro e instância de contêiner foi criado.

#### b) Carregar Dados

- Em importados os dados selecionei "Amostras" e encontrei "Hotel-sample".

---

### 3. **Indexar os Documentos com Azure AI Search**

#### a) Assistente de Importação de Dados

- Utilizado para criar automaticamente:
  - Fonte de dados
  - Índice de pesquisa
  - Indexador
    
---

### 4. **Consultar o Índice de Pesquisa**

#### a) Usando o Search Explorer

- Acessado via portal do Azure no recurso Azure AI Search.
- Consultas realizadas:

#### b) Busca Avançada com Palavra-Chave
- Uma busca foi realizada com a palavra-chave **"30"** para encontrar referências a idade, quantidade ou qualquer valor numérico nos textos analisados:
```json
{
    "search": "30",
    "count": true
}
```

- Esta consulta retornou avaliações onde a palavra "30" apareceu, podendo estar associada a:
  - Idade do cliente
  - Quantidade de dias sem reclamações
  - Horário da visita (ex: 30 minutos)
  - Qualquer outro uso contextual da palavra

---

