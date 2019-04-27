[![N|Solid](https://i.imgur.com/HihuZh1.png)](https://www.liberedu.com.br)  

# Desafio - Estágio Full Stack Developer - Liber

## Index
- [ Introdução ](#introdução)
- [ Backend ](#backend)
- [ Frontend ](#frontend)
- [ Linguagens ](#linguagens)
- [ Apresentação ](#apresentação)
- [ Avaliação ](#avaliação)
- [ Envio ](#envio)


## Introdução

Na Liber recebemos diversos pedidos de aula das mais variadas disciplinas diariamente. Sua tarefa será implementar uma versão simplificada de um sistema de agendamento de aulas para os nossos alunos.

## Backend

Para o backend você deverá implementar uma API RESTful com as seguintes características:

### **Rota para cadastro de um usuário com nome, email e senha**

#### POST /api/cadastro

| Argumento | Descrição                                 | Tipo   |
| --------- | ----------------------------------------- | ------ |
| nome      | Nome do usuário como no máximo 20 digitos | string |
| email     | Email do usuário                          | string |
| senha     | Senha do usuário com no máximo 10 digitos | string |

### **Rota para login de um usuário com email e senha**

#### POST /api/login

| Argumento | Descrição                                 | Tipo   |
| --------- | ----------------------------------------- | ------ |
| email     | Email do usuário                          | string |
| senha     | Senha do usuário com no máximo 10 digitos | string |

**OBS:** O login deverá ser stateless (via token com tempo de expiração determinado e de sua escolha) - dica: Utilize JWT

### **Rota para armazenar um pedido de aula do usuário** (requer autenticação)

#### POST /api/requests

| Argumento   | Descrição                                             | Tipo       |
| ----------- | ----------------------------------------------------- | ---------- |
| subject_id  | Identificador da disciplina da aula no banco de dados | int        |
| date        | Dia da aula                                           | YYYY-MM-dd |
| time        | Horário da aula                                       | HH:mm      |
| description | Descrição das necessidades do aluno para a aula       | string     |

### **Rota para ver os pedidos de aula do usuário** (requer autenticação)

#### GET /api/requests

| Parâmetros  | Descrição                                       |
| ----------- | ----------------------------------------------- |
| id          | ID da disciplina                                |
| subject     | Nome da disciplina                              |
| date        | Dia da aula                                     |
| time        | Horário da aula                                 |
| description | Descrição das necessidades do aluno para a aula |

### **Rota para ver um pedido de aula do usuário** (requer autenticação)

#### GET /api/requests/{request_id}

| Parâmetros  | Descrição                                       |
| ----------- | ----------------------------------------------- |
| id          | ID da disciplina                                |
| subject     | Nome da disciplina                              |
| date        | Dia da aula                                     |
| time        | Horário da aula                                 |
| description | Descrição das necessidades do aluno para a aula |

**Observações**:

- A validação de todos os dados enviados na interação com a API é obrigatória

- Utilize um padrão de respostas JSON único ao longo de toda a sua aplicação para os casos de sucesso e erro nas requisições.

## Frontend

Para o frontend você deverá implementar as seguintes interfaces:

- Uma tela para **cadastro** do usuário com nome, email e senha
  - Caso já exista um usuário com o email enviado, uma mensagem de erro deve ser mostrada

- Uma tela para **login** do usuário com email e senha
  - Quando o usuário digitar dados inválidos uma mensagem de erro deve ser mostrada

- Uma **tela inicial**, acessível apenas para usuários autenticados, dando bem-vindo ao usuário, utilizando seu nome de cadastro. Além disso, deverá existir um menu, presente não só nessa página como em todas as outras, com as seguintes opções: Home, Meus Pedidos e Novo Pedido

- Uma tela, acessível apenas para usuários autenticados, onde é possível **marcar uma aula** ao preencher as seguintes informações: disciplina, dia, horário e, opcionalmente, a descrição.

- Uma tela, acessível apenas para um usuário autenticado, onde o mesmo pode **visualizar os pedidos** que já realizou.
  - Caso não existam pedidos, uma mensagem deve ser exibida para informar o usuário.

- Uma tela para **visualizar apenas a informação de um pedido qualquer** pertencente ao usuário autenticado
  - Caso o usuário tente acessar um pedido não pertencente a ele, o mesmo é redirecionado para a página principal.

**Bônus**: Validação frontend dos dados que você julgar necessário.

## **Linguagens**

Para o backend da aplicação: **PHP** ou **Javascript** (NodeJS) com banco de dados **SQL** ou **NOSQL** de sua escolha. Na Liber, trabalhamos com PHP, utilizando o framework **Laravel**, junto de um banco de dados em **MySQL**, mas você está livre para escolher o que preferir dentro do mencionado.

Para o frontend, você deverá utilizar o **ReactJS**.

## **Apresentação**

É obrigatório que além do código desenvolvido, exista uma documentação detalhando como você chegou na solução apresentada. Além disso, é fundamental expor um passo a passo de como executar as aplicações desenvolvidas. 

Serão considerados como bônus:

- A conteneirização das aplicações utilizando Docker.

- Testes unitários, de integração e end-to-end

## **Avaliação**

Independente da tecnologia utilizada, a avaliação será centrada na sua capacidade de organização e arquitetura de software, seguindo boas práticas de programação orientada a objetos, com a utilização de design patterns.

Dica: Clean Code

## **Envio**

Você deverá fazer um fork desse repositório e enviar um pull request com a sua solução.

## **Observações Finais e Prazo**

O desafio deverá ser entregue em até 5 dias após o recebimento.
