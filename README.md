# 🐬 MySQL para Aulas de Banco de Dados

Ambiente **Docker** pronto para ensinar Banco de Dados a um aluno.
Com um único comando, sobe um servidor **MySQL 8.4** já com um banco de exemplo (`dbestudo`) populado, e uma interface web (**Adminer**) para explorar as tabelas sem instalar nada.

> **Objetivo:** o aluno não perde tempo instalando e configurando MySQL. Ele clona o repositório, roda o Docker e já começa a praticar SQL em um banco com dados realistas.

---

## 📦 O que tem aqui

```
mysql-aula/
├── docker-compose.yml     # MySQL 8.4 + Adminer
├── init/
│   ├── 01-schema.sql      # Criação das tabelas
│   └── 02-dados.sql       # Dados de exemplo
└── README.md
```

Os scripts da pasta `init/` rodam **automaticamente** na primeira vez que o container sobe.

---

## ✅ Pré-requisitos

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) (Windows/Mac) ou Docker Engine (Linux)
- Opcional: um cliente SQL como [DBeaver](https://dbeaver.io/), MySQL Workbench ou extensão do VS Code

---

## 🚀 Como usar

```bash
git clone <url-deste-repositorio>
cd mysql-aula
docker compose up -d
```

Aguarde alguns segundos até o MySQL ficar pronto (`docker compose ps` deve mostrar `healthy`).

### Acessos

| Onde | Endereço | Usuário | Senha |
|---|---|---|---|
| Adminer (navegador) | http://localhost:8080 — servidor: `mysql` | `lucas` | `123` |
| Cliente SQL (DBeaver, Workbench…) | `localhost`, porta **3307** | `lucas` | `123` |
| Administrador | idem | `root` | `123` |
| Terminal | `docker exec -it mysql-aula mysql -u lucas -p123 dbestudo` | — | — |

