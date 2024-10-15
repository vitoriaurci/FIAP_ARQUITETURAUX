Storytelling sobre o problema
Um homem decide comprar uma casinha de cachorro online com entrega rápida. Após algumas semanas, a casinha chega, mas ele percebe que o tamanho está errado. Tentando devolver o produto, ele enfrenta dificuldades no processo de devolução online, o que o deixa frustrado. Sem sucesso pela internet, ele vai até uma pet shop local, onde finalmente consegue resolver o problema e trocar a casinha por uma de tamanho adequado.

O que esperamos aprender com esse projeto?
De forma geral, esta iniciativa nos trará:

Uma visão mais aprofundada da arquitetura de um dos principais provedores de material e alimentos para animais.
Maior entendimento sobre os padrões utilizados.
Oportunidades no setor.
Perguntas que precisamos responder:
Algumas perguntas essenciais são:

Como são geradas divergências na devolução?
Quais são as restrições de regulamentação nacional e internacional?
Quais são os requisitos contábeis e fiscais?
O que meu cliente busca?
Principais riscos:
Os principais riscos relacionados à devolução de produtos incluem:

Prazo de devolução, que deve atender à Lei do Consumidor.
Risco de fraude: é importante identificar se o produto já foi usado.
Armazenamento adequado.
Devoluções incorretas.
Regulamentações do MAPA.
Processos de destruição ou reuso de produtos devolvidos.
Plano para aprender e reduzir riscos:
Plano de Aprendizagem:

Identificar e mapear todos os processos de devolução.
Realizar entrevistas com stakeholders para entender pontos críticos.
Validar as regulamentações nacionais e internacionais aplicáveis.
Plano para Reduzir Riscos:

Estabelecer processos de auditoria para devoluções.
Implementar sistemas de rastreamento para evitar fraudes.
Garantir que o armazenamento e a logística estejam em conformidade com regulamentações.
Stakeholders e expectativas:
Clientes: Esperam uma devolução rápida e eficiente.
Lojas físicas: Querem uma integração perfeita com o estoque e os pedidos online.
Equipe de TI: Espera que a arquitetura seja escalável e fácil de manter.
Principais problemas que podem surgir:
Insatisfação dos clientes devido a falhas nas devoluções.
Inconsistência de estoque.
Atrasos ou erros nos reembolsos.
Componentes da arquitetura:
Autoatendimento (Totem de Loja): Processa devoluções diretamente nas lojas físicas.
ERP Frente de Loja: Sincronizado com o ERP Central para atualizar o estoque.
ERP Central: Gerencia estoque, pedidos, logística e processos financeiros.
Pedidos: Sistema de vendas online que integra a devolução de produtos.
Plataforma de Eventos: Coordena a comunicação entre os sistemas.
Gateway de Pagamentos: Processa os reembolsos.
Motor de Processamento de Imagens: Valida imagens dos produtos devolvidos.
API Gateway (Outbound): Gerencia comunicações com sistemas externos.
Requisitos importantes:
Sincronização entre sistemas: Garante que o estoque esteja atualizado em tempo real.
Segurança de dados: Protege transações financeiras e informações sensíveis.
Eficiência no processamento de devoluções: Fundamental para uma boa experiência do cliente.
Escalabilidade: A arquitetura deve crescer junto com a empresa.
Integração com sistemas de terceiros: Facilita o processamento de reembolsos.
Diagrama ajuda a raciocinar sobre:
Integração de sistemas: Mostra como os diferentes sistemas se integram.
Processo de devoluções: Visualiza o fluxo desde o início até o reembolso.
Padrões essenciais no diagrama:
Arquitetura Orientada a Serviços (SOA): Facilita a manutenção e escalabilidade.
Plataforma de Eventos: Desencadeia ações entre os sistemas de forma assíncrona.
Sincronização de Estoque: Garante consistência nos dados de estoque.
Padrões ocultos:
Desacoplamento através de APIs: Facilita a troca de sistemas de terceiros.
Processamento assíncrono: Permite operações contínuas, mesmo com algumas operações em andamento.
Arquiteturas no padrão C4:
Nível Contexto: Visão geral de como o sistema interage com o ambiente externo.
Nível Container: Mostra os principais contêineres (sistemas e serviços) envolvidos.
Nível Componente: Detalha os componentes internos de cada contêiner.
