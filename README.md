# Sistema de Controle de Atividades Escolares

Projeto desenvolvido para a disciplina de Sistemas Operacionais II, utilizando Docker, Docker Compose e APIs em Python (Flask), seguindo o modelo de microserviços.

---

## Tecnologias Utilizadas

- Python 3.10
- Flask
- Docker
- Docker Compose

---

## Objetivo

Desenvolver um sistema distribuído capaz de:

- Gerenciar alunos
- Gerenciar atividades
- Associar atividades aos alunos
- Executar tudo via containers Docker

---

## Arquitetura do Projeto

O sistema foi dividido em dois microserviços:

- API de Alunos → Porta 5000
- API de Atividades → Porta 5001

Cada serviço roda em um container separado.

---

## Estrutura do Projeto

```bash
projeto-escola/
├── alunos_api/
├── atividades_api/
└── docker-compose.yml
````

---

## Como Executar o Projeto

Na raiz do projeto, execute:

```bash
docker compose up --build
```

Após isso, os serviços estarão disponíveis em:

* [http://localhost:5000](http://localhost:5000) (Alunos)
* [http://localhost:5001](http://localhost:5001) (Atividades)

---

## Endpoints da API

### Alunos

* GET /alunos → Lista alunos
* POST /alunos → Cadastra aluno
* GET /alunos/{id} → Busca aluno

### Atividades

* GET /atividades → Lista atividades
* POST /atividades → Cadastra atividade
* GET /atividades/aluno/{id} → Lista por aluno
* PUT /atividades/{id}/concluir → Concluir atividade

---

## Testes da API (Thunder Client / Postman)

### Listar alunos

Requisição:
GET [http://localhost:5000/alunos](http://localhost:5000/alunos)

Resultado:
<img width="1436" height="755" alt="image" src="https://github.com/user-attachments/assets/953c63e3-8e57-4e70-864e-e2ddde38a0b0" />


---

### Cadastrar aluno

Requisição:
POST [http://localhost:5000/alunos](http://localhost:5000/alunos)

Body:

```json
{
  "nome": "Carlos",
  "curso": "Computação"
}
```

Resultado:
<img width="1432" height="740" alt="image" src="https://github.com/user-attachments/assets/71b567dd-10d7-4ec6-a710-a72eef21c0f4" />

---

### Listar atividades

Requisição:
GET [http://localhost:5001/atividades](http://localhost:5001/atividades)

Resultado:
<img width="1434" height="743" alt="image" src="https://github.com/user-attachments/assets/042f914e-e138-4519-ae2b-b28a556dba3b" />

---

### Cadastrar atividade

Requisição:
POST [http://localhost:5001/atividades](http://localhost:5001/atividades)

Body:

```json
{
  "titulo": "Trabalho Docker",
  "descricao": "Criar containers",
  "aluno_id": 1
}
```

Resultado:
<img width="1427" height="785" alt="image" src="https://github.com/user-attachments/assets/1efa8108-68fd-484f-9648-af56da31a48d" />


---

### Concluir atividade

Requisição:
PUT [http://localhost:5001/atividades/1/concluir](http://localhost:5001/atividades/1/concluir)

Resultado:
<img width="1433" height="746" alt="image" src="https://github.com/user-attachments/assets/a4d0391d-8e2f-45c3-9036-0dbeba660006" />

---

## Organização dos Prints

Crie uma pasta chamada "prints" na raiz do projeto com os arquivos:

```bash
projeto-escola/
├── prints/
│   ├── listar-alunos.png
│   ├── cadastrar-aluno.png
│   ├── listar-atividades.png
│   ├── cadastrar-atividades.png
│   ├── concluir-atividade.png
```

---

## Autor

Lucas Cabrio

```
```
