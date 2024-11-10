# DIO_DESF_CLOUDE
Um README explicativo sobre alguns passos para criação de um assistente virtual
Resolução do aprendizado sobre Assistente de Delivery com AWS Step Functions e Bedrock:

## Introdução:

1.	Importância do Assistente Virtual:
o	Assistentes virtuais com IA generativa oferecem automação e respostas rápidas, essenciais para o sucesso empresarial.
o	Benefícios incluem atendimento 24/7 e liberação de recursos humanos para tarefas estratégicas.
2.	Personalização e Baixa Latência:
o	Assistentes eficazes precisam de acesso à base de conhecimento específica da empresa.
o	Personalizar o modelo de IA e garantir baixa latência nas respostas é fundamental para uma experiência fluida e positiva ao usuário.
3.	Técnicas de Engenharia de Prompt:
o	Técnicas como ReAct e Prompt Chaining são essenciais para direcionar a IA e aprimorar a interação.
________________________________________
## Visão Geral da Solução:

1.	Arquitetura Serverless e Ferramentas Utilizadas:
o	A solução utiliza AWS Lambda e AWS Step Functions para orquestrar múltiplos modelos através do Amazon Bedrock.
o	A combinação de Lambda URL e Lambda Web Adapter permite respostas em streaming, otimizando a latência.
2.	Flexibilidade e Experimentação com Múltiplos Modelos:
o	A solução permite fácil experimentação e mudança entre modelos, aumentando a adaptabilidade da IA ao contexto.
________________________________________
## Funcionamento da Solução:

1.	Orquestração de Tarefas com Step Functions:
o	A AWS Lambda aciona a Step Functions, que por sua vez chama a API do Bedrock para respostas em streaming.
o	Com a Resposta em Stream, o tempo de resposta (TTFB) é otimizado, melhorando a experiência do usuário.
2.	Engenharia de Prompt com Prompt Chaining:
o	Prompt Chaining organiza a interação por subtarefas e permite personalização através de parâmetros de prompt.
o	Lambda executa prompts complexos, usando modelos mais poderosos como Claude, otimizando a responsividade e precisão.
3.	Divisão de Tarefas para Eficiência:
o	Cada tarefa no Step Functions usa prompts específicos e concisos, possibilitando foco em objetivos menores e controle sobre tokens, reduzindo latência.

________________________________________
## Aplicações Práticas:

1.	RAG (Recuperação e Geração de Respostas):
o	O Step Functions usa Bedrock para aprimorar a entrada com palavras-chave e buscar informações em bases de conhecimento, resultando em respostas rápidas e contextuais.
2.	Router (Roteamento de Fluxo de Trabalho):
o	Com Step Functions, a arquitetura atua como um roteador que separa cenários baseados em dados (determinísticos) e não determinísticos, como workflows de retenção.
3.	Testes A/B:
o	A arquitetura permite testes rápidos e ajustes nas Step Functions, sem necessidade de modificar o código, otimizando processos.
4.	Chamadas de API:
o	Dados em formatos como JSON e XML podem ser gerados pelos LLMs e usados pelo Step Functions para executar tarefas, permitindo que Lambda forneça respostas explicativas em streaming.
