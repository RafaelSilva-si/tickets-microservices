# E-commerce com Microserviço

Este projeto exemplifica os conceitos e fundamentos dos microserviços, implementados utilizando Node.js e Express. O foco principal é a criação de uma aplicação de vendas de tickets para eventos. Adotando práticas de Clean Code e TDD (Test-Driven Development), este projeto não apenas oferece uma implementação funcional, mas também destaca a importância da organização do código e da escrita de testes robustos.

Sinta-se à vontade para explorar este repositório e mergulhar nas ideias por trás desta implementação. Aproveite para examinar como os microserviços podem ser estruturados e como princípios de desenvolvimento limpo e TDD podem ser aplicados em um contexto real.

## Serviços

### User
O módulo de usuários gerencia informações de usuários, incluindo os campos Id, Nome, Email e Telefone. Ele permite a criação, leitura, atualização e exclusão (CRUD) de registros de usuários, garantindo que cada usuário tenha um identificador único (Id), um nome, um endereço de email e um número de telefone para contato.

- POST / USER (name, email, password, confirmPassword, phone)
- GET /USER (params para filtro: (name, email, phone))
- GET /USER/:ID
- PATCH /USER/:ID (name, email, password, confirmPassword, phone)
- DELETE /USER/:ID
  
### Auth
O módulo de autenticação gerencia funções essenciais para a segurança do sistema. Ele permite a autenticando-os durante o login com suas credenciais (como email e senha) e gerando tokens de acesso. Além disso, posteriormente será vai ser possivel que o módulo facilita o logout, invalidando tokens e encerrando sessões de usuário. Ele também verifica tokens de autenticação para assegurar que apenas usuários autorizados acessem recursos protegidos. Em caso de esquecimento de senha, o módulo oferece a recuperação de senha, permitindo que usuários redefinam suas senhas de forma segura. Dessa forma, o módulo de autenticação protege dados e funcionalidades sensíveis, garantindo que apenas usuários autenticados tenham acesso a determinadas partes do sistema.

- POST /AUTH (email, password)
  
### Events
O módulo de evento gerencia informações de eventos, incluindo os campos Id, titulo, capacidade endereço e etc.... Ele permite a criação, leitura, atualização e exclusão (CRUD) de registros de eventos, garantindo que cada evento tenha um identificador único (Id), um titulo, um endereço do evento.

- POST / EVENT (
  title
  date
  description
  capacity
  cover
  galerry
  category
  status)

- GET /EVENT (params para filtro: (title, date, category))
- GET /EVENT/:ID
- PATCH /EVENT/:ID (
  title
  date
  description
  capacity
  cover
  galerry
  category
  status)

- DELETE /EVENT/:ID

### Cart

O módulo de evento gerencia informações do Cart, incluindo os itemID, userID, qtd e etc.... Ele permite a criação, leitura, atualização e exclusão (CRUD) de registros de cart, garantindo que cada cart tenha um identificador único (Id), um status, e items adicionados.

- POST / CART (
  cartID (optional)
  itemID
  userID
  qtd
  )

- GET /CART/:ID - Busca detalhes do cart com items.

- PATCH /CART/ - Edita Qtd do item.
(
  id
  qtd
)

- DELETE /CART/:ID Limpa todo o Carrinho

### API Gateway
O API Gateway atua como um ponto de entrada para diferentes serviços do sistema, funcionando como um proxy. Ele recebe as requisições dos clientes e as encaminha para o serviço apropriado, abstraindo a complexidade do sistema backend. Além disso, o API Gateway pode realizar tarefas como autenticação, autorização, balanceamento de carga, roteamento de solicitações e agregação de respostas, melhorando a eficiência e a segurança das comunicações entre clientes e serviços backend.
## Boas Práticas

### TDD
Esse projeto usa TDD (Test-Driven Development), uma metodologia onde os testes são escritos antes do código. Isso garante que cada nova funcionalidade seja testada desde o início, ajudando a prevenir bugs e melhorar a qualidade do software.
Você pode ver mais em um artigo que fiz sobre TDD: [Entendendo o TDD](https://dev.to/rafa_dev/tdd-2mpa).

### Eslint
Este projeto usa ESLint, uma ferramenta essencial para identificar e corrigir problemas em JavaScript e TypeScript. Além disso, usamos TypeScript para garantir uma tipagem estática robusta, aumentando a segurança e a manutenção do código. Também integramos o Prettier para formatação automática do código, assegurando um estilo consistente em todo o projeto. Essa combinação de ferramentas ajuda a manter o código limpo, consistente e livre de erros, seguindo as melhores práticas de desenvolvimento.
### CI
Este projeto utiliza CI (Integração Contínua) com GitHub Actions. GitHub Actions automatiza tarefas de desenvolvimento, como testes e deploys, sempre que novas alterações são enviadas ao repositório. Isso garante que o código seja continuamente testado e integrado, facilitando a detecção precoce de bugs e mantendo a qualidade e a integridade do projeto ao longo do tempo.


## Instalação com Docker
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
1. Clone o repositório.
2. Navegue até o diretório do projeto.
3. Em um terminal rode o comando `docker compose -f docker-compose.yml up`
4. Aplicação rodando em http://localhost:3000/.


![1627616883421](https://user-images.githubusercontent.com/77937182/157932279-c8aad7d0-0778-43c0-be52-b7e175d56835.gif)
