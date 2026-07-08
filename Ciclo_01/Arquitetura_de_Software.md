# Arquiterura de Software
É o esqueleto e a fundação de um sistema. Ela define como o sistema será estruturado, quais serão seus componentes principais e, 
principalmente, como esses componentes vão se comunicar entre si.

Se o código é o tijolo e a fiação elétrica de uma casa, a arquitetura é a planta azul do engenheiro. 
Ela decide onde ficam as colunas de sustentação para garantir que o prédio não caia se você decidir construir mais três andares no futuro.

### Os Três Pilares da Arquitetura
Para entender o que um arquiteto de software faz, pense nestas três decisões principais:
1. **Divisão de Responsabilidades**: O sistema não é um bloco único de código. A arquitetura decide como dividi-lo. Por exemplo: uma parte cuida do banco de dados, outra processa os pagamentos e outra lida com a interface que o usuário vê.
2. **Padrões de Comunicação**: Como essas partes conversam? Elas mandam mensagens diretas (APIs síncronas)? Elas usam um intermediário para enviar avisos em segundo plano (mensageria por eventos, como o AWS EventBridge)?
3. **Atributos de Qualidade (Requisitos Não-Funcionais)**: É aqui que a arquitetura brilha. O código pode funcionar perfeitamente, mas a arquitetura garante que ele consiga:
  * **Escalar**: Aguentar 10 mil acessos simultâneos sem cair.
  * **Ser Seguro**: Proteger dados sensíveis contra invasões.
  * **Ser Flexível**: Permitir que novos recursos sejam adicionados sem quebrar o que já existe.

### Arquiteturas Comuns no Mercado
Não existe "arquitetura perfeita", existe a arquitetura certa para o problema certo. Veja os dois modelos mais discutidos hoje:
 * **Monolito**: O sistema inteiro é construído como um único bloco. É excelente para projetos iniciais e automações porque é fácil de desenvolver e implantar. O risco é que, se uma parte falhar ou ficar lenta, o sistema todo pode cair.
 * **Microserviços**: O sistema é dividido em pequenos serviços independentes que rodam sozinhos. Se o serviço de emissão de relatórios falhar, o usuário ainda consegue fazer login e usar o resto do sistema. É altamente escalável, mas adiciona bastante complexidade na comunicação e na infraestrutura (geralmente exigindo boas práticas de computação em nuvem).

### Monólitos vs. Microsserviços
Em vez de focar em "qual é o melhor", estude a **jornada de evolução** de um sistema.
 * **Arquitetura Monolítica**: Todo o código (módulos, banco de dados, interface) roda como uma única unidade.
  * O que focar: Entenda que monólitos são ótimos para começar (MVP), fáceis de testar e implantar. O problema surge com o crescimento: se uma parte do sistema quebra ou precisa de mais recursos, você tem que escalar o   monólito inteiro.
 * **Microsserviços**: O sistema é dividido em pequenos serviços independentes que se comunicam via rede (APIs). Cada um cuida de uma função de negócio e pode ter seu próprio banco de dados.
  * O que focar: Eles resolvem o problema de escala e permitem que times trabalhem de forma independente. Porém, trazem uma complexidade gigante de rede, latência e consistência de dados.

**Como estudar**: Pegue um sistema simples (como um e-commerce). Desenhe mentalmente como ele funciona como um monólito (uma única aplicação) e depois como ele seria dividido em serviços (Serviço de Autenticação, Serviço de Catálogo, Serviço de Pagamento).

### Padrões Arquiteturais (MVC, Clean Architecture, DDD)
O segredo aqui é entender o princípio da Separação de Preocupações (separation of concerns). Cada padrão resolve isso em um nível diferente.
 * MVC (Model-View-Controller): Padrão de interface/aplicação.
   * Model: Os dados e as regras de negócio.
   * View: O que o usuário vê (interface).
   * Controller: O intermediário que recebe o clique do usuário, avisa o Model e atualiza a View.

 * **Clean Architecture (Arquitetura Limpa)**: Focada na independência do código. O núcleo da sua aplicação (regras de negócio) fica no centro e não deve depender de frameworks, bancos de dados ou ferramentas externas. Tudo que é externo fica nas camadas de fora.
 * **DDD (Domain-Driven Design)**: Não é só uma arquitetura, é uma filosofia de design focada no "Domínio" (o problema real do negócio). Estude conceitos como Bounded Contexts (delimitar onde um termo significa uma coisa) e Ubiquitous Language (usar os mesmos termos que as pessoas de negócios usam no código).

**Como estudar**: Implemente uma funcionalidade simples (ex: criar um usuário) usando apenas MVC. Depois, tente reescrever essa mesma funcionalidade aplicando os conceitos de camadas da Clean Architecture. Você vai notar como o código fica mais isolado e fácil de testar.

### Design de APIs (REST, HTTP)
API é o contrato de comunicação. Foque em entender as regras desse contrato para que ele seja intuitivo.
 * **REST** e **JSON**: REST é um estilo arquitetural que usa o próprio protocolo HTTP para transferir dados. O JSON é o formato de texto padrão (leve e legível) usado para estruturar esses dados.
 * **Verbos HTTP (As Ações)**:
   * **`GET`**: Buscar informações (não altera dados).
   * **`POST`**: Criar um novo recurso.
   * **`PUT`**: Atualizar um recurso existente (substituição completa).
   * **`PATCH`**: Atualizar parcialmente um recurso.
   * **`DELETE`**: Remover um recurso.
* **Códigos de Status (As Respostas)**:
   * **`200 OK`**: Deu tudo certo.
   * **`201 Created`**: Sucesso, e algo novo foi criado (geralmente resposta de um POST).
   * **`400 Bad Request`**: Erro do cliente (ex: faltou um campo obrigatório no formulário).
   * **`401 Unauthorized`**: O cliente precisa se autenticar (fazer login).
   * **`404 Not Found`**: O recurso solicitado não existe.
   * **`500 Internal Server Error`**: Erro no servidor (o código quebrou ou o banco caiu).

**Como estudar**: Use ferramentas como Postman ou Insomnia. Crie uma API falsa (pode usar o `json-server` no Node.js ou ferramentas online) e pratique fazer requisições disparando cenários diferentes para ver os códigos de status mudando na prática (ex: tentar buscar um ID que não existe para ver o `404`).

### Estrutura de pastas

```
src/
│
├── domain/                    # CAMADA 1: Regras de Negócio Fundamentais (Entidades)
│   └── entities/
│       └── user.js            # Regras da entidade Usuario (ex: validação de email)
│
├── use-cases/                 # CAMADA 2: Casos de Uso (O que o sistema faz)
│   └── create-user.js         # Lógica específica para criar um usuário
│
├── adapters/                  # CAMADA 3: Adaptadores (Conectores)
│   ├── controllers/
│   │   └── user-controller.js # Traduz a requisição HTTP para o Caso de Uso
│   └── repositories/
│       └── user-repository.js # Interface/Contrato de como salvar no banco
│
└── infra/                     # CAMADA 4: Infraestrutura (Ferramentas externas)
    ├── database/
    │   └── mongo-user-repo.js # Implementação real do banco de dados (MongoDB)
    └── web/
        └── server.js          # Configuração do servidor express/fastify
```

## Design de uma API REST
Desenhar o contrato de uma API antes de escrever o código economiza horas de refatoração.

Para um **Sistema de Biblioteca**, vamos trabalhar com duas entidades (recursos) principais: Livros (**`books`**) e Empréstimos (**`loans`**). 
Em REST, sempre usamos substantivos no plural para identificar os recursos.

Aqui está o design completo da API com os verbos, rotas, corpos de requisição (**`body`**) e códigos de status HTTP corretos para cada cenário:

#### Gerenciamento de Livros (**`/books`**)
Listar Livros
 * **Método**: **`GET`**
 * **Rota**: **`/books`**
 * **Resposta de Sucesso**: **`200 OK`** (Retorna um array com todos os livros).

#### Buscar Detalhes de um Livro
 * **Método**: **`GET`**
 * **Rota**: **`/books/:id`** (Ex: **`/books/45`**)
 * **Respostas Possíveis**:
   * **`200 OK`** se o livro existir (Retorna o objeto do livro).
   * **`404 Not Found`** se o ID não existir no sistema.

#### Cadastrar um Novo Livro
  * **Método**: **`POST`**
  * **Rota**: **`/books`**
  * **Request Body (JSON)**:
    ```json
    {
      "title": "O Senhor dos Anéis",
      "author": "J.R.R. Tolkien",
      "isbn": "978-8551002490"
    }

    ```
    
 * **Respostas Possíveis**:
   * `201 Created` se for salvo com sucesso (Retorna o livro criado com o ID gerado).
   * `400 Bad Request` se o cliente esquecer de enviar o title ou se o isbn for inválido.
   * `401 Unauthorized` se o usuário tentando cadastrar não estiver logado (ex: um visitante anônimo).

#### Atualizar um Livro (Substituição Total)
  * **Método**: `PUT`
  * **Rota**: `/books/:id`
  * **Request Body (JSON)**: Envia todos os campos modificados ou não.
  * **Resposta de Sucesso**: `200 OK`.

#### Deletar um Livro
  * **Método**: DELETE
  * **Rota**: /books/:id
  * **Respostas Possíveis**:
    * `200 OK` ou `204 No Content` (Sucesso, sem conteúdo para retornar).
    * `404 Not Found` se tentar deletar um livro que já não existe.

### Operações de Empréstimo (`/loans`)
Aqui entra o "pulo do gato" do design RESTful. Em vez de criar uma rota com verbo no nome (como `/solicitarEmprestimo` ou `/devolverLivro`), nós tratamos o **Empréstimo** como um recurso próprio.

#### Solicitar Empréstimo de um Livro
Criar um empréstimo significa dar um POST na coleção de empréstimos.
  * **Método**: POST
  * **Rota**: /loans
  * **Request Body (JSON)**:

```json
{
  "userId": "usr_9921",
  "bookId": "45"
}

```

#### * Respostas Possíveis:
   * **`201 Created`** se o empréstimo for gerado.
   * **`400 Bad Request`** se o livro solicitado já estiver emprestado para outra pessoa (erro de negócio).
   * **`404 Not Found`** se o **`bookId`** ou o **`userId`** não existirem no sistema.

### Devolver um Livro (Atualizar o Empréstimo)
Quando o usuário devolve o livro, o empréstimo foi modificado (ganhou uma data de devolução e o status mudou para concluído). Usamos `PATCH` porque estamos atualizando apenas uma parte do empréstimo.

   * **Método**: `PATCH`
   * **Rota**: `/loans/:id/return` (Nota: Extensões na rota como `/return` são aceitas no REST clássico para ações específicas em recursos).
   * **Respostas Possíveis**:
     * `200 OK` indicando que a devolução foi registrada.
     * `400 Bad Request` se o livro já tiver sido devolvido anteriormente.

**Cenário Extra: O Erro do Servidor** (**`500 Internal Server Error`**)
Imagine que o usuário faz um `GET /books`, mas o banco de dados da biblioteca caiu naquele exato momento. O seu código vai capturar essa falha interna e deve retornar obrigatoriamente um `500 Internal Server Error` com uma mensagem amigável (sem expor dados sensíveis do banco):

```json
{
  "error": "Desculpe, ocorreu um erro interno no nosso sistema. Tente novamente mais tarde."
}
```
