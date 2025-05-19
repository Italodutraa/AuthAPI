FirstAuthAPI - API de Autenticação com NestJS

Este é um projeto de API de autenticação utilizando NestJS, JWT, Prisma e PostgreSQL com suporte para Docker. A aplicação permite o registro de usuários, login e proteção de rotas usando tokens JWT.

🛠️ Tecnologias Utilizadas

NestJS - Framework Node.js para construção de APIs escaláveis.

TypeScript - Superset do JavaScript com tipagem estática.

Prisma - ORM moderno e type-safe.

PostgreSQL - Banco de dados relacional utilizado via Docker.

JWT (JSON Web Token) - Autenticação baseada em tokens.

Docker - Contêiner para o banco de dados PostgreSQL.

📦 Instalação e Configuração

Clone o repositório:

git clone https://github.com/Italodutraa/FirstAuthAPI.git
cd FirstAuthAPI

Instale as dependências:

npm install

Crie o arquivo .env:

DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/database"
JWT_SECRET="sua-chave-secreta"

Suba o banco de dados com Docker:

docker-compose up -d

Execute as migrations:

npx prisma migrate dev

Inicie o servidor:

npm run start:dev

🛠️ Uso da API

Cadastro (SignUp):

Endpoint: POST /auth/signup

Body:

{
"name": "Seu Nome",
"email": "email@example.com",
"password": "senha123"
}

Login (SignIn):

Endpoint: POST /auth/signin

Body:

{
"email": "email@example.com",
"password": "senha123"
}

Endpoint Protegido:

Use o token JWT no header:

{
"Authorization": "Bearer SEU_TOKEN"
}

📂 Estrutura do Projeto

src/
├── auth/
│ ├── auth.controller.ts
│ ├── auth.service.ts
│ ├── auth.guard.ts
│ └── dto/
│ ├── sign-up.dto.ts
│ └── sign-in.dto.ts
├── prisma/
│ ├── prisma.service.ts
│ └── schema.prisma
├── main.ts
└── app.module.ts

📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.
