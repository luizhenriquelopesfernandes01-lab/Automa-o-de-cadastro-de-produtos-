
# Cadastro Automático de Produtos

Automação em Python que faz login em um sistema e cadastra produtos automaticamente a partir de uma tabela CSV, usando pandas e PyAutoGUI. Projeto desenvolvido durante o curso de Python da Hashtag Treinamentos.

## O que o projeto faz

1. Abre o navegador e acessa o sistema.
2. Faz login com e-mail e senha.
3. Lê a tabela de produtos no arquivo `produtos.csv`.
4. Cadastra cada produto, preenchendo os campos um a um.

## Tecnologias

- Python
- pandas
- PyAutoGUI


## Configuração

Antes de rodar, edite o início do arquivo `main.py`:

- `LINK`: endereço do sistema.
- `EMAIL` e `SENHA`: dados de acesso.
- As posições de clique (x e y) conforme a resolução da sua tela.

Para descobrir as posições, use `pyautogui.position()` no terminal.

## Formato do CSV

O arquivo `produtos.csv` precisa ter as colunas: codigo, marca, tipo, categoria, preco, custo e obs.

## Segurança

Mova o mouse para o canto superior esquerdo para abortar a automação.
