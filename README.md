# FirstAuthAPI - API de Autenticação com NestJS

Este é um projeto de API de autenticação utilizando NestJS, JWT, Prisma e PostgreSQL com suporte para Docker. A aplicação permite o registro de usuários, login e proteção de rotas usando tokens JWT.

---

## 🛠️ Tecnologias Utilizadas

- **NestJS** - Framework Node.js para construção de APIs escaláveis.
- **TypeScript** - Superset do JavaScript com tipagem estática.
- **Prisma** - ORM moderno e type-safe.
- **PostgreSQL** - Banco de dados relacional utilizado via Docker.
- **JWT (JSON Web Token)** - Autenticação baseada em tokens.
- **Docker** - Contêiner para o banco de dados PostgreSQL.

---

## 📦 Instalação e Configuração

1. **Clone o repositório:**

```bash
git clone https://github.com/Italodutraa/FirstAuthAPI.git
cd FirstAuthAPI
```

2. **Instale as dependências:**

```bash
npm install
```

3. **Crie o arquivo `.env`:**

```env
DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/database"
JWT_SECRET="sua-chave-secreta"
```

4. **Suba o banco de dados com Docker:**

```bash
docker-compose up -d
```

5. **Execute as migrations:**

```bash
npx prisma migrate dev
```

6. **Inicie o servidor:**

```bash
npm run start:dev
```

---

## 🛠️ Uso da API

- **Cadastro (SignUp):**

  - Endpoint: `POST /auth/signup`
  - Body:

    ```json
    {
      "name": "Seu Nome",
      "email": "email@example.com",
      "password": "senha123"
    }
    ```

- **Login (SignIn):**

  - Endpoint: `POST /auth/signin`
  - Body:

    ```json
    {
      "email": "email@example.com",
      "password": "senha123"
    }
    ```

- **Endpoint Protegido:**

  - Use o token JWT no header:

    ```json
    {
      "Authorization": "Bearer SEU_TOKEN"
    }
    ```

---

## 📂 Estrutura do Projeto

```
src/
├── auth/
│   ├── auth.controller.ts
│   ├── auth.service.ts
│   ├── auth.guard.ts
│   └── dto/
│       ├── sign-up.dto.ts
│       └── sign-in.dto.ts
├── prisma/
│   ├── prisma.service.ts
│   └── schema.prisma
├── main.ts
└── app.module.ts
```

---

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
