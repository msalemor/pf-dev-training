# Promptflow Developer Training

Promptflow developer training

## What is Promptflow

"Prompt flow is a suite of development tools designed to streamline the end-to-end development cycle of LLM-based AI applications, from ideation, prototyping, testing, evaluation to production deployment and monitoring. It makes prompt engineering much easier and enables you to build LLM apps with production quality."

## Setup

- Recommended: Python 3.9
- Required packages:
  - promptflow >=1.1.0
  - promptflow-tools>=1.0.0

## Samples Got-Yas

- Most samples reference a model name, gpt-35-turbo. You can edit this model name in the flow to work with existing models you may have deployed.
- You may get an error when trying to create a connection
```text
This error was raised due to keyring can’t find an available backend to store keys. For example, macOs Keychain and Windows Credential Locker are valid keyring backends.

To resolve this issue, install the third-party keyring backend or write your own keyring backend, for example:

pip install keyrings.alt
```

### Connections

Connections store the connection secrets. In your local development environment, the connections are persisted to the secret stores (Windows/Mac OS). In Linux, you many need to run `pip install keyrings.alt` to install a secret store. 

In Azure AI, connections can be configured to be shared across the entire workspace. Secrets associated with connections are securely persisted in the corresponding Azure Key Vault, adhering to robust security and compliance standards.

#### Connection operations

- Creating a connection
```bash
pf connection create --file ./my_chatbot/openai.yaml --set api_key=<your_api_key> --name open_ai_connection
```

Reference:
- https://microsoft.github.io/promptflow/reference/pf-command-reference.html#pf-connection


### Creating a simple Chat flow

```bash
# Create a flow
pf flow init --flow <flow-name>

# Create a chat flow
pf flow init --flow <flow-name> --type chat
```

#### Types of flows

- Standard
- Chat
- Evaluation

**Note:** As a general guideline, if you are building a chatbot that needs to maintain conversation history, try chat flow. In most other cases, standard flow should serve your needs.

### Execution

### LLM Blocks - Jinja2 templates

### Python Blocks

## Comments

- You can achieve fantastic results with templates.
- For full power, you need to add Python modules.
- Python options do not have to rely on the Promptflow infrastructure. For example, you can create a langchain or Semantic Kernel Python code that calls its own connection settings and configuration.

## Promptflow is suitable for

- Teams that have experience with prompt engineering, LLM models, tokens, token limits, and Python development, and want to leverage their skills.
- Teams that prefer to create flows in code using a configuration file, from Python code, authoring templates, or by making adjustments from a visual designer.

## Reference

- [Promptflow](https://microsoft.github.io/promptflow/index.html)
