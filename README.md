# Atendente Virtual 

Este projeto consiste no desenvolvimento de um chatbot inteligente e automatizado para triagem e atendimento inicial de clientes da **Gesso Galo**. Utilizando o ecossistema **LangChain** e modelos de linguagem de código aberto (LLMs), o sistema é capaz de interpretar solicitações de orçamento (identificando o tipo de serviço de gesso/drywall e a metragem do ambiente) e gerar respostas comerciais extremamente personalizadas, cordiais e profissionais de forma instantânea.

## Tecnologias e Ferramentas Utilizadas

* **Python**: Linguagem base para o desenvolvimento do script.
* **LangChain**: Framework utilizado para a orquestração de componentes de IA e Engenharia de Prompts.
    * `langchain-core`: Para estruturação de templates de prompts (`ChatPromptTemplate`) e parsers de saída (`StrOutputParser`).
    * `langchain-huggingface`: Para integração simplificada e execução de modelos hospedados no Hugging Face.
* **Hugging Face Hub**: Infraestrutura de nuvem para execução da LLM.
* **Qwen 2.5 (7B Instruct)**: Modelo de linguagem (LLM) de código aberto de última geração, escolhido por sua alta capacidade de seguir instruções precisas (Instruction-Following) e excelente desempenho em tarefas textuais.

## Arquitetura da Solução (LCEL Chain)

O projeto foi construído utilizando a **LangChain Expression Language (LCEL)**, que permite criar fluxos de execução de forma declarativa e limpa através do operador pipe (`|`). 

O fluxo de dados segue a seguinte esteira:
```text
Dados do Cliente (Dicionário) -> ChatPromptTemplate -> HuggingFaceEndpoint (LLM) -> StrOutputParser -> Resposta Final
