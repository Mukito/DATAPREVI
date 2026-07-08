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


Monólitos vs. Microsserviços
Em vez de focar em "qual é o melhor", estude a jornada de evolução de um sistema.

Arquitetura Monolítica: Todo o código (módulos, banco de dados, interface) roda como uma única unidade.

O que focar: Entenda que monólitos são ótimos para começar (MVP), fáceis de testar e implantar. O problema surge com o crescimento: se uma parte do sistema quebra ou precisa de mais recursos, você tem que escalar o monólito inteiro.

Microsserviços: O sistema é dividido em pequenos serviços independentes que se comunicam via rede (APIs). Cada um cuida de uma função de negócio e pode ter seu próprio banco de dados.

O que focar: Eles resolvem o problema de escala e permitem que times trabalhem de forma independente. Porém, trazem uma complexidade gigante de rede, latência e consistência de dados.

Como estudar: Pegue um sistema simples (como um e-commerce). Desenhe mentalmente como ele funciona como um monólito (uma única aplicação) e depois como ele seria dividido em serviços (Serviço de Autenticação, Serviço de Catálogo, Serviço de Pagamento).

2. Padrões Arquiteturais (MVC, Clean Architecture, DDD)
O segredo aqui é entender o princípio da Separação de Preocupações (separation of concerns). Cada padrão resolve isso em um nível diferente.

MVC (Model-View-Controller): Padrão de interface/aplicação.

Model: Os dados e as regras de negócio.

View: O que o usuário vê (interface).

Controller: O intermediário que recebe o clique do usuário, avisa o Model e atualiza a View.

Clean Architecture (Arquitetura Limpa): Focada na independência do código. O núcleo da sua aplicação (regras de negócio) fica no centro e não deve depender de frameworks, bancos de dados ou ferramentas externas. Tudo que é externo fica nas camadas de fora.

DDD (Domain-Driven Design): Não é só uma arquitetura, é uma filosofia de design focada no "Domínio" (o problema real do negócio). Estude conceitos como Bounded Contexts (delimitar onde um termo significa uma coisa) e Ubiquitous Language (usar os mesmos termos que as pessoas de negócios usam no código).

Como estudar: Implemente uma funcionalidade simples (ex: criar um usuário) usando apenas MVC. Depois, tente reescrever essa mesma funcionalidade aplicando os conceitos de camadas da Clean Architecture. Você vai notar como o código fica mais isolado e fácil de testar.

3. Design de APIs (REST, HTTP)
API é o contrato de comunicação. Foque em entender as regras desse contrato para que ele seja intuitivo.

REST e JSON: REST é um estilo arquitetural que usa o próprio protocolo HTTP para transferir dados. O JSON é o formato de texto padrão (leve e legível) usado para estruturar esses dados.

Verbos HTTP (As Ações):

GET: Buscar informações (não altera dados).

POST: Criar um novo recurso.

PUT: Atualizar um recurso existente (substituição completa).

PATCH: Atualizar parcialmente um recurso.

DELETE: Remover um recurso.

Códigos de Status (As Respostas):

200 OK: Deu tudo certo.

201 Created: Sucesso, e algo novo foi criado (geralmente resposta de um POST).

400 Bad Request: Erro do cliente (ex: faltou um campo obrigatório no formulário).

401 Unauthorized: O cliente precisa se autenticar (fazer login).

404 Not Found: O recurso solicitado não existe.

500 Internal Server Error: Erro no servidor (o código quebrou ou o banco caiu).

Como estudar: Use ferramentas como Postman ou Insomnia. Crie uma API falsa (pode usar o json-server no Node.js ou ferramentas online) e pratique fazer requisições disparando cenários diferentes para ver os códigos de status mudando na prática (ex: tentar buscar um ID que não existe para ver o 404).
