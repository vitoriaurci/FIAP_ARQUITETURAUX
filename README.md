# FIAP_ARQUITETURAUX

Story Telling sobre o problema                                        																					Um homem decide comprar uma casinha de cachorro online com entrega rápida. Após algumas semanas, a casinha chega, mas ele percebe que o tamanho está errado. Tentando devolver o produto, ele enfrenta dificuldades no processo de devolução online, o que o deixa frustrado. Sem sucesso pela internet, ele vai até uma pet shop local, onde finalmente consegue resolver o problema e trocar a casinha por uma de tamanho adequado. 
			
O que esperamos aprender com esse projeto?																									
De forma Geral, esta iniciativa nos trará uma visão mais aprofundada da arquitetura presente em um dos principais provedores de material e alimentos para animais, trará um maior entendimento sobre os padrões utilizados e uma visão de oportunidades no setor.

Que perguntas precisamos que sejam respondidas?																									
 Algumas perguntas essenciais surgem, como: 'Como são geradas divergências na devolução?', 'Quais são as restrições de regulamentação nacional e internacional?', 'Quais são os requisitos contábeis e fiscais?', e 'O que meu cliente busca?'. Essas dúvidas guiam nosso processo de entendimento.

Quais são os nossos principais riscos?																										
os principais riscos relacionados à devolução de produtos. Entre eles estão o prazo de devolução, que deve atender à Lei do Consumidor; o risco de fraude, onde é importante identificar se o produto já foi usado; a necessidade de armazenamento adequado; devoluções incorretas, regulamentações do MAPA, e processos de destruição ou reuso dos produtos devolvidos."


Crie um plano para aprender o que precisamos para responder a perguntas específicas.
Crie um plano para reduzir riscos.																												
Quem são as partes interessadas?																															
O que eles esperam ganhar?																												
Quem são os usuários?																																					
O que eles estão tentando realizar?																																			
Qual o pior que pode acontecer?																																													
Os principais problemas que podem surgir durante o processo de devolução. Falhas nas devoluções podem gerar insatisfação dos clientes. A inconsistência de estoque, causada pela falta de sincronização entre as lojas físicas e o estoque central, pode resultar em discrepâncias de inventário. E, por fim, atrasos ou erros nos reembolsos podem frustrar os clientes, impactando a experiência geral.
Desenhe uma arquitetura (Modelo Freeform - Versão inicial)
![Picture1](https://github.com/user-attachments/assets/b83c2e3b-f686-4491-a109-8bd251f2fdd1)


Faça uma descrição de cada um dos componentes que você desenhou	
Autoatendimento (Totem de Loja): 
Responsável por processar devoluções diretamente nas lojas físicas. O cliente interage com o totem, onde pode verificar o QR code, confirmar a devolução e atualizar o estoque da loja.

ERP Frente de Loja: 
Sistema que gerencia o estoque das lojas físicas. Está sincronizado com o ERP Central e o Totem de Autoatendimento, garantindo que as devoluções sejam refletidas tanto no estoque local quanto no central.

ERP Central: 
Sistema centralizado que gerencia o estoque global, os pedidos, a logística e os processos financeiros da empresa. Ele recebe atualizações de devoluções vindas das lojas físicas e do e-commerce, além de notificar o módulo financeiro e logístico sobre as alterações necessárias.

Pedidos: 
Sistema de vendas online onde o cliente pode solicitar o cancelamento de um pedido, enviar fotos para validação, escolher a loja de devolução e acompanhar o status do cancelamento. Ele está integrado ao sistema de Pedidos Backend, que coordena o processamento de devoluções e atualiza o status dos pedidos.

Plataforma de Eventos: 
Gerencia a comunicação entre os diferentes sistemas (lojas físicas, e-commerce e ERP). Quando um cancelamento é confirmado, gera um evento para a criação do QR code e coordena as interações entre os módulos.

Gateway de Pagamentos: 
Serviço externo responsável por processar os reembolsos das devoluções. Ele comunica diretamente com o ERP e a plataforma de e-commerce para garantir que o pagamento seja processado corretamente.

Motor de Processamento de Imagens: 
Utilizado para validar as imagens dos produtos devolvidos que são enviadas pelos clientes no processo de devolução online.

API Gateway (Outbound): 
Gerencia as comunicações com sistemas externos, como o Gateway de Pagamentos. Ele garante que os dados de reembolso e devolução sejam enviados e recebidos corretamente.

																									
Descreva requisitos que você (s) considera importante e por quê?																														
Sincronização entre sistemas (ERP Central e ERP Frente de Loja):
Importante para garantir que o estoque esteja atualizado em tempo real, evitando erros de disponibilidade 
e garantindo que as devoluções sejam processadas de forma precisa.
Segurança de dados (API Gateway e Plataforma de Eventos):
Fundamental para proteger transações financeiras e informações sensíveis dos clientes, 
garantindo a integridade e confidencialidade das interações entre os diferentes sistemas.
Eficiência no processamento de devoluções (Autoatendimento e Motor de Processamento de Imagens):
Essencial para garantir que os clientes tenham uma experiência rápida e sem fricções ao realizar devoluções, 
seja na loja ou online.
Escalabilidade (Plataforma de Eventos):
A arquitetura precisa ser capaz de lidar com um número crescente de devoluções e transações,
 à medida que a empresa cresce ou em períodos de alta demanda.
Integração com sistemas de terceiros (Gateway de Pagamentos):
Importante para garantir que os reembolsos sejam processados de forma eficiente e sem erros, 
minimizando a insatisfação do cliente.
																													
Sobre o que o diagrama ajuda você a raciocinar/pensar?																									
Integração de Sistemas: O diagrama facilita o entendimento de como os diferentes sistemas da empresa (lojas físicas, e-commerce, ERP central e sistemas externos) se integram para realizar um processo completo de devolução.
Processo de Devoluções: Ele também ajuda a visualizar como o fluxo de devoluções é orquestrado, desde a solicitação inicial até o reembolso final, passando por diversas verificações e validações.
																													
Quais são os padrões essenciais no diagrama?																																	
Arquitetura Orientada a Serviços (SOA):
Os componentes são organizados como serviços independentes que se comunicam via APIs e eventos. Isso facilita a manutenção e a escalabilidade.
Plataforma de Eventos:
O uso de eventos para desencadear ações entre os sistemas permite uma arquitetura mais desacoplada, onde as operações podem ser realizadas de forma assíncrona.
Sincronização de Estoque:
A sincronização entre o ERP Central e o ERP Frente de Loja é um padrão que garante consistência nos dados de estoque entre todos os pontos de venda.
																				
Existem padrões ocultos?																													
Padrões Ocultos:
Desacoplamento através de APIs:
O uso de API Gateway para gerenciar a comunicação com sistemas externos é um padrão oculto, mas importante, que permite que a empresa troque sistemas de terceiros sem grandes modificações na arquitetura interna.
Processamento assíncrono:
O uso de uma Plataforma de Eventos sugere que o processamento das devoluções pode ser feito de forma assíncrona, permitindo que o sistema continue operando mesmo que algumas operações estejam em andamento (ex.: validação de fotos e geração de QR codes).
																																
Qual é o Metamodelo?																																					
Pode ser discernido no diagrama único?																																		
O diagrama está completo?																																			
Poderia ser simplificado e ainda assim ser eficaz?																											
Houve alguma discussão importante que vocês tiveram como equipe?																															
Que decisões sua equipe teve dificuldade para tomar?																															
Que decisões foram tomadas sob incerteza?																																		
Houve algum ponto de decisão sem retorno que o forçou a desistir de uma determinada escolha?																														
Desenhe 3 Arquiteturas com o projeto que você desenvolveu na aula em cada uma das camadas do C4; (Subir somente a Imagem jpg/jpeg)
Nível Contexto
Nível Container
Nível Componente
