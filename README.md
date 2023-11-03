# To-Do List App

Este é um projeto de lista de tarefas (to-do list) desenvolvido com Vue.js, Tailwind CSS e JSON Server. A aplicação permite aos usuários gerenciar tarefas, incluindo adição, edição, exclusão e marcação de tarefas como concluídas. Os dados das tarefas são persistidos utilizando o JSON Server para simular uma API de armazenamento e recuperação.

## Funcionalidades

- Exibição de lista de tarefas com status de conclusão.
- Adição de novas tarefas via formulário.
- Edição e exclusão de tarefas existentes.
- Marcação de tarefas como concluídas, atualizando seu status.
- Persistência de dados utilizando o JSON Server.

## Requisitos Técnicos

- **Vue.js 3:** Utilizado como framework de front-end.
- **Tailwind CSS:** Framework de estilização para a aplicação.
- **JSON Server:** Simulação de API para armazenamento de dados.
- **Vue Router:** Utilizado para criar rotas de navegação entre as páginas.

## Como Executar

Siga estes passos para executar o projeto localmente:

### Pré-requisitos

- Node.js e NPM instalados na sua máquina.

### Passos

1. Clone este repositório:
```bash
  git clone https://github.com/matheusfmendes/to-do-list
```

2. Acesse o diretório do projeto:
```bash
cd To-do-list
```
3. Instale as dependências:
```bash
npm install
```

4. Inicie o servidor JSON:
```bash
json-server --watch db.json
```
5. Inicie a aplicação:
```bash
npm run serve
```

6. Abra o navegador e acesse `http://localhost:8080` para visualizar a aplicação.

## Contribuição

Se deseja contribuir com melhorias, sinta-se à vontade para abrir um Pull Request, seguindo as diretrizes de contribuição deste projeto.


## Licença

Este projeto está licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para mais detalhes.

