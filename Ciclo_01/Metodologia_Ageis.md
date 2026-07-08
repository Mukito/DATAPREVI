# Metodologia Ágeis

São uma forma de gerenciar projetos — muito comum na TI, mas usada em várias áreas — focada em **flexibilidade, entregas rápidas e colaboração**.

Em vez de tentar planejar todo o projeto do início ao fim logo no primeiro dia (o que costuma dar errado porque as coisas mudam), o trabalho é dividido em ciclos curtos.

O grande marco dessa cultura foi o **Manifesto Ágil** (2001), que estabeleceu quatro valores principais:
  * **Pessoas e interações** mais do que processos e ferramentas.
  * **Software (ou produto)** funcionando mais do que documentação abrangente.
  * **Colaboração com o cliente** mais do que negociação de contratos.
  * **Responder a mudanças** mais do que seguir um plano inicial rígido.

Na prática, isso significa que a equipe trabalha em blocos de tempo fixos (geralmente de 2 a 4 semanas) 
chamados de Sprints ou iterações. Ao final de cada ciclo, entrega-se uma parte real e utilizável do projeto. 
Isso permite colher feedbacks cedo e corrigir a rota sem desperdiçar meses de trabalho.

As metodologias mais famosas que aplicam esses conceitos são:
  * **Scrum**: Organiza o trabalho em Sprints, com papéis definidos (como o Scrum Master e o Product Owner) e reuniões diárias rápidas.
  * **Kanban**: Focado na visualização do fluxo de trabalho, geralmente usando quadros com colunas como "A Fazer", "Em Andamento" e "Concluído", para evitar gargalos.

## Scrum: A Estrutura Rígida (Foco em Ritmo)
O Scrum funciona em ciclos fechados chamados **Sprints** (que duram de 1 a 4 semanas). Nada entra no meio de uma Sprint sem negociação. Ele é baseado em 3 pilares cobrados em prova: **Transparência, Inspeção e Adaptação.**

A estrutura do Scrum se divide exatamente em: **3 Papéis, 5 Eventos e 3 Artefatos** (Regra do 3-5-3).

### Os 3 Papéis (Quem faz o quê)
  * **Product Owner (PO)**: É o dono do produto. Ele dita o que deve ser feito. É o único responsável por priorizar a lista de desejos do cliente (Product Backlog). Ele foca no valor de negócio.
  * **Scrum Master (SM)**: É o guardião do processo. Ele não manda na equipe; ele ajuda o time a entender o Scrum, remove barreiras/impedimentos e blinda o time de distrações externas. É um líder servidor.
  * **Developers (Time de Desenvolvimento)**: Quem coloca a mão na massa. Eles decidem como vão fazer o trabalho. O time é multifuncional (tem tudo o que precisa para entregar o trabalho) e autogerenciável.

### Os 5 Eventos (Os rituais)
  1. **A Sprint**: É o evento maior que envelopa todos os outros. É o ciclo de tempo onde o trabalho acontece.
  2. **Sprint Planning (Planejamento)**: Reunião no início da Sprint. O PO diz o que é prioritário, e os Developers definem o que conseguem entregar naquele ciclo, criando o Sprint Backlog.
  3. **Daily Scrum (Reunião Diária)**: Reunião de 15 minutos, em pé, para alinhar o trabalho das últimas 24 horas e planejar as próximas 24 horas.
  4. **Sprint Review (Revisão)**: No final da Sprint, o time mostra o produto pronto (o incremento) para os clientes e stakeholders coletarem feedback.
  5. **Sprint Retrospective (Retrospectiva)**: Acontece após a Review e antes da próxima Planning. O foco aqui é melhorar o processo interno e as relações do time (o que funcionou, o que deu errado e como melhorar).

### Os 3 Artefatos (As entregas físicas/visuais)
  * **Product Backlog**: A lista mestre, viva e priorizada de tudo o que o produto precisa. Quem manda aqui é o PO.
  * **Sprint Backlog**: A lista de tarefas que o time escolheu para fazer naquela Sprint específica, mais o plano para entregá-las. Quem manda aqui são os Developers.
  * **Incremento**: A soma de todos os itens do Product Backlog completados durante a Sprint. Ele precisa estar utilizável e atingir a Definição de Concluído (DoD - Definition of Done).

## Kanban: O Fluxo Contínuo (Foco em Eficiência)
Ao contrário do Scrum, o Kanban não tem papéis obrigatórios, nem ciclos fixos (Sprints). Ele gerencia o fluxo de trabalho de forma contínua. 
Se o Scrum é um trem que sai da estação de 2 em 2 semanas, o Kanban é uma esteira rolante que nunca para.

Os dois conceitos mais cobrados em prova são:

### O Fluxo (Visualização)
O Kanban se baseia em puxar o trabalho conforme a capacidade do time, em vez de empurrar prazos. 
A ferramenta visual clássica é o quadro Kanban (com colunas como A Fazer, Em Andamento, Revisão, Concluído). 
O objetivo é dar visibilidade total: qualquer um olha e sabe onde o trabalho está agarrado (gargalos).

### Limitação de WIP (Work in Progress / Trabalho em Progresso)
Essa é a maior pegadinha do Cebraspe. **O Kanban limita o trabalho em andamento**.
  * **Como funciona**: O time define que a coluna "Em Andamento" só pode ter, no máximo, 3 tarefas por vez (WIP = 3). Se já houver 3 tarefas ali, ninguém pode puxar uma tarefa nova de "A Fazer", mesmo que esteja ocioso. Os membros do time precisam se unir para terminar o que já começou.
  * **O lema do Kanban é**: "Pare de começar, comece a terminar."

