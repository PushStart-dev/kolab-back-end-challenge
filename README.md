# Teste para Backender Kolab

## Instruções Gerais

- Utilize as tecnologias NestJS, Typescript, TypeORM e Swagger.
- Implemente a funcionalidade de autenticação utilizando JWT e Cookie.
- Deve ser possível testar os endpoints usando o Swagger.
- Utilize um banco de dados de sua preferência para armazenar os dados.
- Crie uma API onde deve ser possível:
   - Realizar o CRUD de usuários de uma empresa;
      - `id` (uuid)
      - `username`
      - `password`
      - `parentUserId` (pode ser null)
   - Login;
   - Logout;
   - Listar toda a árvore de funcionários seguindo a hierarquia cadastrada (usando o parentUserId) (NÃO usar o TypeORM para isso, faça via código direto).

## Endpoints

### Autenticação de Usuário

   - Forneça os seguintes endpoints públicos:
     - `POST /auth/register`: Cria um novo usuário no sistema.
     - `POST /auth/login`: Recebe credenciais de usuário (username e password), retorna um token JWT além de persisti-lo no Cookie no browser.

### Endpoints Protegidos com Autenticação

   - Proteja os seguintes endpoints para que apenas usuários autenticados possam acessá-los:
     - `POST /auth/logout`: Apaga o JWT do Cookie invalidando a sessão.
     - `GET /users/:id`: Retorna os detalhes de um usuário específico.
     - `PUT /users/:id`: Atualiza os dados de um usuário existente.
     - `DELETE /users/:id`: Remove um usuário existente.
     - `GET /users/tree`: Retorna a árvore de usuários de acordo com o parentUserId.

## Entrega do Teste

- **Projeto:**
   - Crie um repositório Git público ou privado (nos dê acesso se for privado);
   - ou nos envie ZIP com o projeto.

- **README:**
  - Inclua no README explicações de como rodar o teste.
  - Detalhe como realizar a autenticação e utilizar os endpoints protegidos.

# Bônus

Caso você tenha feito o teste até, já está bom, de verdade... Mas se quiser ir além, sinta-se a vontade para demostrar seu conhecimento ou aprender! 👍

- O banco pode ser criado com migration.
- Escreva testes automatizados para garantir a funcionalidade correta dos endpoints implementados e proteção com autenticação.
- Complemente o README informações sobre como rodar os testes automatizados.
- Criar o projeto como um workspace [NX](https://nx.dev/getting-started/intro):
   - Separe o códgo em 2 aplicativos: `user` e `auth`
   - A parte da lógica da autenticação deve ficar em UMA lib separada:
      - O pacote `user` deve usar a lib para validar a sessão
      - O pacote `auth` deve usar a lib para criar a sessão
- Configure o deploy do ambiente de desenvolvimento local para simular AWS com APIGateway + Lambda usando o [serverless-offline](https://www.serverless.com/plugins/serverless-offline).
- NÃO É NECESSÁRIO SUBIR O CÓDIGO NA AWS!

# Observações Finais

- Priorize a qualidade do código e a funcionalidade correta sobre a velocidade de entrega. Uma entrega parcial que está caprichada será bem avaliada.
- Dúvidas? Decida o que fazer usando o seu bom senso. Interpretação faz parte do teste. 👿
- Lembre-se do README!
- Boa sorte!
