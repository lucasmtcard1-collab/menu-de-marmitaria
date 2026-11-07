
# Menu de Marmitaria — Cardápio Digital

Projeto acadêmico da disciplina **N695 — Desenvolvimento de Plataformas Web**, da Universidade de Fortaleza (UNIFOR).

## Objetivo

Desenvolver uma aplicação web de gerenciamento de cardápio para uma marmitaria. O sistema organiza os pratos em categorias e permite o cadastro, a consulta, a edição e a exclusão de registros.

## Tecnologias

- **Node.js** — execução do backend JavaScript.
- **Express 5** — rotas e serviço Web (API REST).
- **PostgreSQL** — armazenamento de categorias e pratos.
- **pg** — comunicação entre a API e o banco de dados.
- **dotenv** — leitura de variáveis de ambiente.
- **HTML/CSS/JavaScript** — interface web em desenvolvimento na pasta `public/`.

## Organização do projeto

- `src/app.js`: inicialização do servidor e registro das rotas.
- `src/routes/`: definição de endpoints HTTP.
- `src/services/`: regras de negócio.
- `src/middlewares/`: tratamento de erros.
- `db/schema.sql`: estrutura das tabelas do PostgreSQL.
- `public/`: arquivos da interface web.
- `.env.example`: exemplo da variável de conexão com o banco.

## Pré-requisitos

- Node.js e npm instalados.
- PostgreSQL disponível (local ou hospedado).
- Uma base de dados PostgreSQL criada e credenciais válidas.

## Como executar localmente

1. Baixe ou clone o repositório:

   ```bash
   git clone https://github.com/MFelipe-dev/menu-de-marmitaria.git
   cd menu-de-marmitaria
   ```

2. Instale as dependências:

   ```bash
   npm install
   ```

3. Crie um arquivo `.env` na raiz com base em `.env.example` e configure a variável `DATABASE_URL` para o seu banco. **Não envie senhas ou o arquivo `.env` ao GitHub.**

   ```env
   DATABASE_URL=postgresql://usuario:senha@host:5432/nome_do_banco
   PORT=3000
   ```

   Ajuste SSL e outros parâmetros de conexão conforme o serviço PostgreSQL utilizado.

4. Execute as instruções SQL de `db/schema.sql` no banco configurado, por exemplo usando o `psql` ou uma ferramenta como pgAdmin.

5. Inicie o servidor:

   ```bash
   npm run dev
   ```

   Ou, para inicialização convencional:

   ```bash
   npm start
   ```

6. Acesse `http://localhost:3000`.

   A interface visual depende da conclusão dos arquivos em `public/`.

## Endpoints da API

| Método | Rota | Ação |
|---|---|---|
| GET | `/api/categorias` | Listar categorias |
| GET | `/api/categorias/:id` | Consultar uma categoria |
| POST | `/api/categorias` | Criar categoria |
| PUT | `/api/categorias/:id` | Editar categoria |
| DELETE | `/api/categorias/:id` | Excluir categoria |
| GET | `/api/categorias/:id/pratos` | Listar pratos da categoria |
| POST | `/api/categorias/:id/pratos` | Criar prato na categoria |
| GET | `/api/pratos/:id` | Consultar um prato |
| PUT | `/api/pratos/:id` | Editar prato |
| DELETE | `/api/pratos/:id` | Excluir prato |

## Regras de negócio

- A categoria tem nome obrigatório e não pode repetir o nome de outra categoria.
- Cada prato pertence a uma categoria.
- O preço do prato deve ser maior que zero.
- O banco impede a exclusão de categoria que ainda contenha pratos vinculados.
- A aplicação deve mostrar mensagens claras para dados inválidos e erros de operações.

**Atenção:** a implementação das regras no código não substitui testes de funcionamento na aplicação publicada.

## Publicação

**Link da aplicação:** [PREENCHER APÓS A PUBLICAÇÃO]

O frontend, a API e a conexão com o PostgreSQL precisam funcionar no ambiente publicado.

## Status das entregas

- [x] Estrutura inicial do backend e rotas de categorias e pratos.
- [x] Esquema das tabelas PostgreSQL.
- [ ] Interface web com as telas mínimas.
- [ ] Testes integrados de CRUD, persistência e validações.
- [ ] Aplicação publicada e acessível publicamente.
- [ ] Capturas de tela e evidências de requisições e respostas.
- [ ] PDF com os 13 tópicos obrigatórios da proposta.

## Equipe e disciplina

- Disciplina: N695 — Desenvolvimento de Plataformas Web
- Instituição: Universidade de Fortaleza (UNIFOR)
- Cenário: 3 — Marmitaria com cardápio digital
- Integrantes: [PREENCHER NOMES E MATRÍCULAS]

## Uso de inteligência artificial

A equipe deve informar no relatório final se utilizou ferramentas de IA generativa, quais foram e para que foram utilizadas.

Este README foi preparado com apoio de ChatGPT e deve ser revisado e validado pela equipe antes da publicação.

## Repositório

https://github.com/MFelipe-dev/menu-de-marmitaria
