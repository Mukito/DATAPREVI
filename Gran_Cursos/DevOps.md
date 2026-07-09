# DevOps (uma junção de Development / Desenvolvimento e Operations / Operações)
Não é apenas uma ferramenta ou um cargo, mas sim uma cultura, um movimento e uma filosofia de engenharia de software.

O principal objetivo do DevOps é **estreitar** a colaboração entre as equipes que **criam o software (Dev)** e as equipes que o **mantêm funcionando em produção (Ops)**, 
permitindo que as empresas entreguem atualizações de forma muito mais **rápida**, **segura** e com maior **qualidade**.

## O Problema que o DevOps Resolve
Antigamente, as equipes trabalhavam em "silos" isolados:
  * **Desenvolvimento**: Queria criar novos recursos e lançá-los o mais rápido possível.
  * **Operações**: Queria estabilidade no sistema, logo, resistia a mudanças frequentes para evitar quedas.

Isso gerava o famoso "na minha máquina funciona", onde o desenvolvedor entregava o código e a equipe de infraestrutura sofria para fazê-lo rodar no servidor. 
O DevOps veio para quebrar esse muro.

## Os Pilares do DevOps (Práticas Principais)
Para fazer essa cultura funcionar, o DevOps se apoia em vários conceitos técnicos fundamentais:
  * **CI/CD (Integração Contínua e Entrega Contínua)**: * Integração Contínua (CI): Os desenvolvedores enviam suas alterações de código para um repositório central várias vezes ao dia. Cada envio é testado automaticamente para garantir que nada foi quebrado.
    * Entrega Contínua (CD): Após passar nos testes, o código é preparado e implantado automaticamente nos ambientes de homologação ou produção.
  * **Infraestrutura como Código (IaC)**: Em vez de configurar servidores, redes e bancos de dados manualmente clicando em painéis, a infraestrutura é definida por meio de arquivos de configuração (código). Ferramentas como Terraform e Ansible fazem isso.
  * **Automação de Testes**: Reduz o trabalho manual e o erro humano. Tudo o que puder ser testado por robôs (testes unitários, de integração, de segurança) deve ser automatizado.
  * **Monitoramento e Log em Tempo Real**: Como os lançamentos são frequentes, é crucial monitorar a saúde da aplicação constantemente (usando ferramentas como Prometheus, Grafana ou Datadog) para identificar e corrigir falhas antes que o usuário perceba.
    
## O Ciclo de Vida DevOps (Infinito)
O processo DevOps é visualizado como um símbolo do infinito ($\infty$), pois é um ciclo contínuo de feedback e melhoria:
1. **Planejar (Plan)**: Definir o que será feito (requisitos, tarefas).
2. **Codificar (Code)**: Desenvolvimento do software.
3. **Construir (Build)**: Compilar o código e gerar as versões/pacotes.
4. **Testar (Test)**: Rodar testes automatizados de qualidade.
5. **Liberar (Release)**: Preparar a versão para entrar em produção.
6. **Implantar (Deploy)**: Colocar a aplicação no ar para os usuários.
7. **Operar (Operate)**: Manter a infraestrutura funcionando e escalável.
8. **Monitorar (Monitor)**: Coletar dados de comportamento e erros para reiniciar o ciclo com melhorias.
  
## Principais Benefícios
  * **Velocidade**: Lançar novos recursos no mercado antes da concorrência.
  * **Confiabilidade**: Menos falhas em produção graças aos testes automatizados.
  * **Escabilidade**: Capacidade de gerenciar sistemas complexos ou em crescimento com menos esforço manual.
  * **Melhor Colaboração**: Ambientes de trabalho mais felizes e produtivos, onde o foco é resolver o problema e não culpar o outro departamento.


