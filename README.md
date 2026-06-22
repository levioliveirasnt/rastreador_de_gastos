# Rastreador de Gastos

![Language](https://img.shields.io/badge/Language-Python-blue.svg)

Aplicação em Python para registrar, organizar e consultar os seus gastos de forma simples e prática pelo terminal.  
Os dados são salvos em arquivo CSV, permitindo persistência entre sessões.  
O projeto foi desenvolvido em Python utilizando as bibliotecas `click` e `rich` para criar uma experiência de terminal mais organizada e interativa.

## Demonstração

![Demonstração do projeto](assets/demo.png)

## Funcionalidades

- Adicionar novos gastos com data, descrição, valor e categoria
- Editar despesas já registradas
- Deletar despesas pelo ID
- Listar todos os gastos com filtros por categoria e mês
- Exibir resumo financeiro mensal por categoria com percentuais
- Salvar e ler dados automaticamente em arquivo CSV

## Instalação e Pré-requisitos

### Pré-requisitos

- Python 3.10 ou superior
- `click`
- `rich`

### Instalação

```bash
git clone https://github.com/levioliveirasnt/rastreador_de_gastos.git
cd rastreador_de_gastos
python -m venv venv
source venv/bin/activate   # Linux / Mac
venv\Scripts\activate      # Windows
pip install -r requirements.txt
```

## Como usar

Veja todos os comandos disponíveis:

```bash
python main.py --help
```

### Comandos disponíveis

| Comando | Descrição |
|---|---|
| `python main.py add` | Adiciona uma nova despesa |
| `python main.py edit <ID>` | Edita uma despesa existente pelo ID |
| `python main.py delete <ID>` | Deleta uma despesa pelo ID |
| `python main.py list` | Lista todas as despesas |
| `python main.py list --category <nome>` | Filtra por categoria |
| `python main.py list --month-year <MM/YYYY>` | Filtra por mês e ano |
| `python main.py resume <MM/YYYY>` | Exibe resumo financeiro do mês |

### Categorias válidas

| Número | Nome |
|---|---|
| 1 | Alimentação |
| 2 | Transporte |
| 3 | Moradia |
| 4 | Saúde |
| 5 | Outros |

---

## Exemplos de uso

### Adicionar uma despesa

```bash
python main.py add
```

O programa vai pedir interativamente:

```text
Digite a data (DD/MM/YYYY): 20/06/2026
Digite uma breve descrição: Almoço restaurante
Digite um valor: 35.90

Escolha a categoria:
1. Alimentação
2. Transporte
3. Moradia
4. Saúde
5. Outros

Digite o número correspondente: 1

🎉 Despesa #1 ('Alimentação') adicionada com sucesso!
```

### Listar todas as despesas

```bash
python main.py list
```

### Listar por categoria

```bash
python main.py list --category Alimentação
```

### Listar por mês e ano

```bash
python main.py list --month-year 06/2026
```

### Editar uma despesa

```bash
python main.py edit 1
```

O programa vai mostrar os valores atuais e pedir os novos.  
Pressione **Enter** para manter o valor atual em qualquer campo.

```text
Data atual: 20/06/2026. Nova data (DD/MM/YYYY) ou Enter:
Descrição atual: Almoço restaurante. Nova descrição ou Enter: Jantar
Valor atual: 35.9. Novo valor ou Enter: 42.00

🎉 Despesa editada com sucesso!
```

### Deletar uma despesa

```bash
python main.py delete 1
```

```text
🎉 Despesa com ID 1 deletada com sucesso!
```

### Resumo financeiro mensal

```bash
python main.py resume 06/2026
```

Exibe uma tabela com os gastos por categoria, valor total e percentual de cada categoria no mês.

## Estrutura do Projeto

```text
rastreador_de_gastos/
├── main.py
├── expenses.csv
├── requirements.txt
├── LICENSE
├── README.md
└── assets/
    └── demo.png
```

### Sobre os arquivos

- **main.py**: contém toda a lógica da aplicação, incluindo os comandos CLI e a manipulação do CSV.
- **expenses.csv**: armazena os dados dos gastos de forma persistente entre sessões.
- **requirements.txt**: lista as dependências externas do projeto (`click` e `rich`).
- **LICENSE**: informa a licença do projeto.
- **assets/**: pasta para imagens e GIFs usados na documentação.

## Licença

Este projeto está licenciado sob a **MIT License**.  
Veja o arquivo [LICENSE](LICENSE) para mais detalhes.