Integração e Visão Estratégica
A reunião definiu a visão clara de integrar as soluções da Deco e da Nekt para criar um ecossistema de dados e workflows que apoie o portfólio da Norte de forma inovadora e eficiente (07:11)

Gustavo destacou a importância de transformar dados dispersos em ferramentas e MCPs (Modelos de Contexto Padronizados) que sejam fáceis de usar e componíveis dentro da plataforma Norte.
A Nekt oferece uma camada analítica com mais de 100 integrações, permitindo consolidar dados de múltiplas fontes para gerar insights próximos ao negócio.
A colaboração pretende oferecer uma solução que automatiza a extração e o uso dos dados para melhorar a tomada de decisão e o dia a dia das startups do portfólio.
A integração de ambas as plataformas será um case de referência, mostrando como dados podem ser aproveitados para acelerar receita, captação e contratação.
Necessidades da Norte e Automação do Portfólio
A Norte precisa de uma ferramenta digital que centralize a gestão do portfólio de 130 empresas para aumentar a eficiência e a comunicação (14:34)

Gustavo explicou que o time da Norte é limitado a 5 pessoas, mas atua em alto contato com as startups, apoiando go-to-market, captação e hiring.
Ele deseja uma plataforma onde founders possam acessar pedidos, fazer updates, e facilitar a troca de informações, reduzindo o trabalho manual e a comunicação fragmentada.
A ideia é usar dados automatizados para gerar alertas sobre métricas críticas como churn, receita e runway, ajudando a identificar startups que precisam de atenção imediata.
Esse sistema permitirá decisões mais rápidas e menos reativas, otimizando o acompanhamento do crescimento e riscos do portfólio.
Desenvolvimento de Produto e Interface
O time da Deco mostrou um protótipo de dashboard e admin extensível que pode ser customizado para monitorar métricas e pedidos de ajuda do portfólio (26:26)

O dashboard permite visualizar comparações entre empresas e acompanhar métricas selecionadas, como faturamento e pedidos de ajuda, com interface ajustável para o branding da Norte.
O admin suporta integração automática com ferramentas como Slack, Airtable e gravações de reuniões para facilitar a geração de relatórios, poupando trabalho manual.
Baby destacou que o framework da Deco permite criar UIs e apps rapidamente, desde que os dados estejam organizados e disponíveis.
O sistema é projetado para ser self-hosted com suporte a bancos SQL variados, garantindo controle e escalabilidade no ambiente da Norte.
Automação Inteligente e Monitoramento de Anomalias
A Nekt está construindo agentes e workflows que usam IA para detectar anomalias em dados operacionais e gerar alertas automáticos, agilizando a resposta a problemas (30:24)

Foi apresentado um exemplo de app que monitora pedidos, cancelamentos e erros via conexão direta com a fonte de dados da VTX, acionando um agente AI para identificar anomalias.
O sistema registra as anomalias no banco e planeja enviar alertas por e-mail ou PagerDuty quando a severidade ultrapassar um limite definido.
Essa abordagem permite transformar dados complexos em insights acionáveis e operacionais, facilitando a manutenção da saúde do negócio.
A expectativa é que esse modelo se torne um template reutilizável para outras empresas do portfólio, acelerando a adoção da solução.
Plano de Ação e Próximos Passos
Foi alinhado um plano para iniciar a integração entre Norte, Deco e Nekt focando em um MVP que automatize insights e facilite a comunicação com os founders (43:19)

O grupo decidiu criar um canal compartilhado para acelerar a troca de ideias e definição dos primeiros casos de uso.
Marcinho foi designado para sugerir o melhor ponto de partida, considerando o uso do framework Deco com os dados da Nekt e os dados já coletados nas reuniões via Firefly.
A proposta é priorizar o desenvolvimento de ferramentas que gerem valor imediato, como a geração automática de relatórios mensais e alertas táticos para o fundo.
Gustavo reforçou o interesse em escalar esse case para outros fundos e clientes, tornando a solução um benchmark da indústria.

Action items
Antônio
Organizar dados das startups para criação de conexões automáticas entre Norte e portfolio (16:00)
Desenvolver APIs para integrar dados analíticos da Nekt com a Deco (20:20)
Trabalhar com equipe para desenvolver apps e dashboards customizados para a Norte (22:15)
Marcinho
Avaliar e sugerir o melhor ponto de partida para o projeto inicial com Deco e Nekt (44:30)
Criar grupo de comunicação para facilitar interação entre as equipes e definir próximos passos (43:30)
Gui
Auxiliar na configuração da conta Deco da Norte e facilitar acesso ao MCP Nekt (40:00)
Contribuir no fornecimento de exemplos e casos de uso rápidos para testes do produto (41:20)
Baby
Desenvolver interface do administrador personalizável para monitoramento do portfólio (27:00)
Ajustar temas visuais para atender identidade da Norte (27:30)
Gustavo
Realizar abordagem personalizada com founders para adotar ferramenta integrada de reportes e métricas (22:30)


Documento de Requisitos do Produto
Objetivo
Desenvolver uma plataforma integrada que facilite a comunicação e a colaboração entre a Norte e suas empresas do portfólio, utilizando dados analíticos e automações para otimizar processos de gestão e tomada de decisão.
Declaração do Problema
Atualmente, a Norte enfrenta desafios na gestão de suas 130 empresas do portfólio, devido à falta de uma ferramenta centralizada que permita o monitoramento eficiente de métricas, a comunicação proativa com os fundadores e a automação de processos. Isso resulta em uma abordagem reativa em vez de proativa, dificultando a identificação de oportunidades e a oferta de suporte adequado às empresas.
Requisitos Funcionais

Dashboard de Performance: 

Criar um painel que agregue dados de desempenho das empresas do portfólio, permitindo visualização de métricas como receita, churn e crescimento.
O painel deve ser personalizável para que os usuários possam escolher quais métricas visualizar.


Automação de Relatórios:

Desenvolver uma funcionalidade que permita a geração automática de relatórios mensais com base nas métricas coletadas, facilitando a comunicação com investidores.
Os relatórios devem ser gerados em formatos amigáveis, como PDF e apresentações.


Integração de Dados:

Implementar coNektores com as principais fontes de dados utilizadas pelas empresas do portfólio, como CRM, plataformas de e-commerce e ferramentas de comunicação.
Garantir que os dados sejam atualizados em tempo real para fornecer informações precisas.


Sistema de Solicitações de Ajuda:

Criar um sistema onde os fundadores possam solicitar ajuda ou recursos específicos, que serão gerenciados e priorizados pela equipe da Norte.
As solicitações devem ser rastreáveis e permitir feedback sobre a eficácia do suporte fornecido.


Notificações e Alertas:

Implementar um sistema de notificações que alerte a equipe da Norte sobre métricas críticas, como queda de receita ou aumento de churn, permitindo intervenções rápidas.
As notificações devem ser configuráveis, permitindo que os usuários escolham quais alertas desejam receber.



Priorização

Alta Prioridade: Dashboard de Performance, Integração de Dados
Média Prioridade: Automação de Relatórios, Sistema de Solicitações de Ajuda
Baixa Prioridade: Notificações e Alertas

Métricas de Sucesso

Adoção da Plataforma: Percentual de empresas do portfólio que utilizam ativamente a plataforma.
Redução do Tempo de Resposta: Diminuição do tempo médio para responder a solicitações de ajuda.
Melhoria nas Métricas de Desempenho: Aumento médio nas métricas de receita e redução do churn nas empresas que utilizam a plataforma.
Satisfação do Usuário: Avaliação de satisfação dos fundadores e da equipe da Norte em relação à facilidade de uso e eficácia da plataforma, medida através de pesquisas periódicas.

Este documento deve servir como um guia para o desenvolvimento da plataforma, assegurando que as necessidades dos usuários sejam atendidas e que a solução proposta traga valor tanto para a Norte quanto para suas empresas do portfólio.
