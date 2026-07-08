# Engenharia de Requisitos
Olhando para um lado técnico fale sobre Engenharia de Requisitos: Técnicas de elicitação, requisitos funcionais vs. não-finais, histórias de usuário os principais tópicos

Olhar para a Engenharia de Requisitos (ER) pelo prisma técnico é entender que ela não é apenas "conversar com o cliente", mas sim a fase mais crítica da engenharia de software: traduzir necessidades de negócios muitas vezes confusas em especificações técnicas precisas, testáveis e implementáveis.

Se errarmos aqui, o código mais bonito do mundo ainda entregará o produto errado. Vamos destrinchar os pilares técnicos da ER:

1. Técnicas de Elicitação de Requisitos
A elicitação é o processo de descobrir, extrair e entender as necessidades do sistema. Tecnicamente, dividimos as abordagens em categorias dependendo do cenário:

Entrevistas e Questionários: Clássicas. Podem ser estruturadas (com roteiro técnico rígido) ou abertas (foco na exploração).

Workshops de JAD (Joint Application Design): Sessões intensivas que reúnem desenvolvedores, analistas e stakeholders na mesma sala para desenhar o escopo em tempo real, reduzindo ruídos de comunicação.

Prototipagem: Criar wireframes ou maquetes interativas (baixa ou alta fidelidade). Tecnicamente essencial para validar a usabilidade e a arquitetura de fluxos antes de escrever código de produção.

Observação de Campo (Etnografia): O analista observa o usuário no ambiente real de trabalho. Excelente para sistemas legados complexos onde o usuário "faz mas não sabe explicar como faz".

Engenharia Reversa / Análise de Documentos: Investigar o banco de dados do sistema antigo, código-fonte ou manuais operacionais existentes para mapear regras de negócio implícitas.

2. Requisitos Funcionais vs. Requisitos Não-Funcionais
Esta é a divisão técnica fundamental da especificação.

Requisitos Funcionais (RF)
Definem o que o sistema deve fazer. São os comportamentos, entradas, processamentos e saídas esperadas.

Exemplo Técnico: "O sistema deve enviar um token JWT de autenticação via cabeçalho HTTP Bearer após a validação bem-sucedida das credenciais do usuário."

Requisitos Não-Funcionais (RNF)
Definem como o sistema deve fazer. Estão ligados a restrições de arquitetura, qualidade, desempenho e segurança (os famosos atributos de qualidade ou "-dades": escalabilidade, portabilidade, confiabilidade).

Exemplo Técnico: "A API de autenticação deve responder a requisições em menos de 200ms (latência) sob uma carga de 10.000 requisições simultâneas (concorrência)."

Critério	Requisitos Funcionais (RF)	Requisitos Não-Funcionais (RNF)
Foco	Funcionalidades e recursos	Restrições e critérios de qualidade
Arquitetura	Molda a lógica de negócios	Molda a infraestrutura e o design arquitetural
Validação	Passa/Falha (A funcionalidade existe?)	Métricas quantitativas (Desempenho, segurança)
3. Histórias de Usuário (User Stories) e Critérios de Aceite
No desenvolvimento ágil (Scrum/Kanban), a documentação pesada de requisitos deu espaço às User Stories, que funcionam como um lembrete para uma conversa técnica. Elas seguem o padrão clássico:

Como um [tipo de usuário],
Eu quero [realizar uma ação / funcionalidade],
Para que [eu obtenha algum valor de negócio].

A Anatomia Técnica: Critérios de Aceite (BDD)
Uma User Story sem critérios de aceite não serve para os desenvolvedores e QAs. Tecnicamente, estruturamos os critérios usando a sintaxe do BDD (Behavior-Driven Development) para que possam ser facilmente automatizados em testes funcionais (utilizando Cucumber ou Gherkin):

Dado (Given): O contexto ou estado inicial do sistema.

Quando (When): A ação executada pelo usuário.

Então (Then): O resultado esperado (a saída ou mudança de estado).

Exemplo Prático:

Dado que o usuário está na página de checkout com um produto de $100 no carrinho,

Quando ele inserir o cupom de desconto "DESCONTO10",

Então o sistema deve aplicar 10% de redução e atualizar o valor total para $90.

4. O Ciclo de Vida Técnico da Engenharia de Requisitos
Para fechar o panorama, a ER não é um evento único, mas um pipeline contínuo:

Elicitação: Coleta e descoberta.

Análise e Negociação: Detecção de conflitos (ex: o cliente quer segurança máxima, mas o orçamento só cobre criptografia padrão) e priorização (usando frameworks como MoSCoW).

Especificação: Transformar o entendimento em artefatos formais (seja uma especificação de caso de uso ou um backlog de Stories estruturado no Jira).

Validação e Verificação: Garantir que os requisitos estão corretos (validação: "construímos o produto certo?") e que atendem aos padrões técnicos de escrita (verificação: "construímos o requisito corretamente, sem ambiguidade?").

Gestão de Requisitos: Rastreabilidade (saber qual linha de código ou caso de teste atende a qual requisito) e controle de mudanças (scope creep).

Do ponto de vista prático e atual de desenvolvimento, qual tem sido o maior desafio no seu fluxo de trabalho: traduzir os requisitos de negócio para o time de desenvolvimento ou conseguir que os stakeholders definam os requisitos sem mudar de ideia a cada sprint?
