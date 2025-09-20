<img src="src/frontend/assets/logo-sem-fundo.png" alt="Logo" width="250" height="250"/>

---

# ✅ ChecklisTI (Dockerized)

![Node.js](https://img.shields.io/badge/Node.js-18+-green)
![MariaDB](https://img.shields.io/badge/MariaDB-11-blue)
![HTML5](https://img.shields.io/badge/HTML5-orange)
![CSS3](https://img.shields.io/badge/CSS3-blueviolet)
![JavaScript](https://img.shields.io/badge/JavaScript-yellow)
![Docker](https://img.shields.io/badge/Docker-Compose-blue)

O **ChecklisTI** é uma aplicação web voltada para o **controle, acompanhamento e gestão do status de sistemas de TI** em empresas de qualquer porte.  

Com o suporte a **Docker**, a aplicação pode ser executada em qualquer ambiente com um único comando, sem necessidade de configurar manualmente banco de dados ou dependências.

---

## 📂 Estrutura do Projeto

src/
├─ backend/ # API Node.js + Express
│ ├─ db.js # Conexão com o banco de dados
│ ├─ package.json # Dependências do backend
│ ├─ schema.sql # Script SQL para criar banco e tabelas
│ ├─ server.js # Ponto de entrada do servidor Node.js
│ ├─ routes/ # Rotas da API
│ └─ utils/ # Funções auxiliares
└─ frontend/ # Interface do usuário (HTML/CSS/JS)
├─ assets/ # Arquivos estáticos
├─ index.html # Página principal
├─ script.js # Scripts JavaScript
└─ style.css # Estilos CSS

yaml
Copy code

---

## 🚀 Tecnologias Principais

- **Backend:** Node.js, Express  
- **Frontend:** HTML5, CSS3, JavaScript (VanillaJS)  
- **Banco:** MariaDB 11  
- **Outros:** Docker & Docker Compose  

---

## 🔧 Pré-requisitos

- [Docker](https://docs.docker.com/get-docker/) instalado  
- [Docker Compose](https://docs.docker.com/compose/) instalado  

---

## ▶️ Como rodar o projeto com Docker

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/itsmemaikon/ChecklisTI.git
   cd ChecklisTI
Suba os containers:

bash
Copy code
docker-compose up --build
Isso irá:

Criar e iniciar um container MariaDB com usuário, senha e banco definidos.

Executar automaticamente o script schema.sql para criar as tabelas (apenas na primeira execução).

Construir e rodar o container do backend Node.js.

Servir o frontend estático.

Acesse a aplicação:

Backend (API): http://localhost:3000

Frontend: http://localhost:3000

🗄️ Banco de Dados
O banco roda dentro do container checklistti_db.

Configurações padrão (definidas no docker-compose.yml):

Host: db (interno ao Docker) ou localhost:3306 (externo)

Database: ChecklisTI

User: checklistti_user

Password: checklistti_pass

Root password: rootpassword

Os dados são persistidos em um volume Docker chamado mariadb_data, portanto não serão perdidos ao reiniciar os containers.

Para acessar o banco via terminal:

bash
Copy code
docker exec -it checklistti_db mariadb -u checklistti_user -pChecklisTI
📝 Fluxo de Desenvolvimento com Docker
Clone o repositório.

Rode docker-compose up --build.

Acesse a aplicação em http://localhost:3000.

Edite o código no host → o backend será reconstruído automaticamente no próximo build.

Para parar os containers:

bash
Copy code
docker-compose down
Para parar e apagar os dados do banco:

bash
Copy code
docker-compose down -v

🗂️ Licença

© 2025 ChecklisTI. Todos os direitos reservados.