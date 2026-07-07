# DATAPREVI
Estudo de concursos

**Analista de Tecnologia da Informação** - Perfil: **Desenvolvimento de Sistemas da DATAPREV**. 
Como a banca histórica ou provável costuma ser a Cebraspe (ou em alguns casos a Cetro/IADES em passados distantes, mas o padrão recente de alto nível é Cebraspe ou FGV), o edital é sempre bastante denso.


## 📊 Peso das Matérias e Estratégia de Foco
O edital de Desenvolvimento de Sistemas se divide essencialmente em 4 grandes pilares. Abaixo está a distribuição recomendada de esforço com base na recorrência das questões:

|Bloco de Conteúdo | Relevância na Prova | Tópicos Críticos (Foco Total) |
|------------------|---------------------|-------------------------------|
| 1. Engenharia de Software e Agilidade | Alta (30%) | Scrum, Kanban, Análise de Pontos de Função (APF), Engenharia de Requisitos, Arquitetura de Software (Microsserviços, REST). |
| 2. Programação e Estruturas | Alta (25%) | Java, Python, Programação Orientada a Objetos (POO), Padrões de Projeto (Design Patterns), APIs RESTful. | 
| 3. Banco de Dados e Dados | Média-Alta (20%) | SQL, Modelagem Entidade-Relacionamento, Transações (ACID), NoSQL e conceitos básicos de Data Lake/DW. | 
| 4. DevOps, CI/CD e Infra | Média (15%) | Docker, Kubernetes, Git, Pipelines CI/CD (Jenkins/GitLab), Testes Automatizados (TDD, BDD). | 
| 5. Governança e Segurança | Baixa-Média (10%) | COBIT, ITIL (foco em incidentes/mudanças), OWASP Top 10, DevSecOps. | 


## 🗺️ O Roadmap de Estudos (Dividido por Ciclos)
Não tente estudar tudo de uma vez. Siga esta ordem lógica para construir a base antes de ir para os tópicos avançados.

### Ciclo 1: A Base Teórica e Arquitetura (Semanas 1 a 4)
Meta: Garantir os pontos das questões conceituais e de processos, que costumam ser literais.
  * **Engenharia de Requisitos**: Técnicas de elicitação, requisitos funcionais vs. não-finais, histórias de usuário.
  * **Metodologias Ágeis**: Scrum (papéis, eventos, artefatos) e Kanban (fluxo, limitação de WIP). A Cebraspe ama misturar conceitos de Scrum e Kanban para tentar te confundir.
  * **Arquitetura de Software**:
    * Arquitetura Monolítica vs. Microsserviços.
    * Padrões arquiteturais (MVC, Clean Architecture, DDD - Domain-Driven Design).
    * Design de APIs: REST, JSON, verbos HTTP e códigos de status (200, 201, 400, 401, 404, 500).

### Ciclo 2: Codificação, POO e Banco de Dados (Semanas 5 a 8)
Meta: Dominar a lógica de código e a persistência de dados. Aqui a banca cobra análise de trechos de código.
  * **Paradigma Orientado a Objetos**: Classes, objetos, herança, polimorfismo, encapsulamento, abstração e os princípios SOLID.
  * **Linguagens de Programação**:
    * **Java**: Sintaxe, coleções (List, Map, Set), tratamento de exceções, concorrência básica.
    * **Python**: Estruturas de dados (listas, dicionários, tuplas), list comprehensions, manipulação de arquivos e bibliotecas comuns.
  * **Padrões de Projeto (Design Patterns GoF)**: Foco nos mais cobrados: Singleton, Factory, Strategy, Observer, Adapter e Facade.
  * **Banco de Dados**:
    * Modelagem Relacional (Chaves primárias/estrangeiras, normalização até a 3ª Forma Normal).
    * Consultas SQL avançadas (JOINs, GROUP BY, subqueries, agregações).
    * Bancos NoSQL: Diferenças entre relacional e não-relacional, tipos de NoSQL (Chave-Valor, Documentos, Grafos, Colunar).

### Ciclo 3: Qualidade, DevOps e Métricas (Semanas 9 a 12)
Meta: Entender como o software é testado, implantado e medido. A DATAPREV modernizou muito seu parque tecnológico, então DevOps é cobrado forte.
  * **Testes de Software**: Testes unitários, de integração, funcionais e de carga. Conceitos de TDD (Test-Driven Development) e BDD.
  * **Gerência de Configuração e CI/CD:**
    * **Git**: Fluxos de trabalho (Gitflow), comandos principais (clone, commit, push, pull, merge, rebase, stash).
    * Pipelines de Integração e Entrega Contínua (CI/CD).
  * **Conteinerização e Orquestração**: Docker (Dockerfile, imagens, volumes, Docker Compose) e conceitos básicos de Kubernetes (Pods, Services, Deployments).
  * **Métricas de Software**: Análise de Pontos de Função (IFPUG) — decore as tabelas de complexidade de ALE/DER e RLR/DER para responder questões de cálculo de PF.

### Ciclo 4: Governança, Segurança e Revisão Fina (Semanas 13+)
Meta: Aparar as arestas e focar em tópicos que exigem mais memorização pura.
  * **Segurança no Desenvolvimento**: OWASP Top 10 (principais vulnerabilidades como Injection, Broken Authentication, Cross-Site Scripting - XSS). Práticas de DevSecOps.
  * **Governança de TI**: Conceitos essenciais do COBIT 2019 e ITIL v4 (foco na transição e operação de serviços).
  * **Revisão por Questões**: Engenharia reversa total. Resolver exaustivamente provas recentes da banca organizadora voltadas para a área de desenvolvimento.

### 💡 Dicas de Execução para a DATAPREV
1. **Código na Prova**: As bancas adoram colocar códigos em Java ou Python com laços de repetição complexos ou pegadinhas de escopo/herança para você adivinhar a saída. Treine ler código no papel sem a ajuda da IDE.
2. **Análise de Pontos de Função (APF)**: Se estiver no edital (e quase sempre está para a DATAPREV por conta dos contratos públicos), garanta o aprendizado de Contagem de Projetos de Desenvolvimento e Melhoria. É uma matéria finita; se você aprender a regra, não erra a questão.
3. **Não subestime a discursiva**: Se o concurso contar com prova discursiva (estudo de caso), ela geralmente abordará Engenharia de Requisitos combinada com Arquitetura de Microsserviços ou modelagem de Banco de Dados. Pratique redigir soluções técnicas de forma clara.


