# Desafio Final: O Otimizador de Prompts da SynapseTech

Descrição: Parabéns! Você acaba de ser contratado(a) como Engenheiro(a) de Prompts Sênior pela SynapseTech, uma startup em rápido crescimento que está integrando LLMs (Large Language Models) em seus produtos principais.

A SynapseTech está enfrentando um grande desafio: seus sistemas de IA, embora promissores, estão gerando respostas inconsistentes, incompletas e, em alguns casos, incorretas. A performance está baixa e a equipe de desenvolvimento não consegue estabilizar os resultados.

Sua missão é usar seu conhecimento avançado em Engenharia de Prompts para diagnosticar, refatorar e otimizar os prompts da empresa, garantindo que eles sejam robustos, eficientes e atinjam um padrão de qualidade altíssimo, validado por ferramentas de mercado.

Objetivo: 

- Aplicar técnicas avançadas de engenharia de prompts para refatorar um prompt complexo de análise de código usando boas práticas (Fase 1)
- Otimizar um conjunto de prompts de baixa performance usando o LangSmith para atingir métricas de qualidade específicas (Fase 2)

Repositório Base: Você receberá um repositório base em Python (utilizando LangChain) que contém:

A estrutura da aplicação.

Os arquivos prompts.yml (alguns vazios, outros com prompts "ruins").

Scripts de teste automatizado (Fase 1).

Scripts de avaliação integrados ao LangSmith (Fase 2).



## Fase 1: Refatoração de Prompt Complexo (Análise de PR)

Cenário: A equipe de DevOps da SynapseTech quer automatizar a criação de release notes. Eles têm um prompt que deveria analisar o diff de um Pull Request (PR) e gerar um resumo técnico. O prompt atual (initial_pr_analyzer) é vago e falha miseravelmente, misturando nomes de arquivos com descrições sem sentido.

Requisitos (Fase 1):

Análise: Estudar o prompt "ruim" fornecido no repositório base.

Refatoração: No arquivo prompts.yml, você deve criar um novo prompt (refined_pr_analyzer) que resolva o problema.

Técnicas Avançadas: Seu novo prompt deve utilizar pelo menos duas das técnicas avançadas vistas no curso (Ex: Tree of Thoughts, Skeleton of Thought, Few-shot Learning com exemplos claros, ou definição de Persona e Contexto muito bem estruturados).

Validação Local: O repositório base contém testes automatizados (python run_tests.py --fase1). Seu prompt deve:

Estar corretamente formatado no prompts.yml.

Conter as variáveis de entrada esperadas (ex: pr_diff, pr_title).

Passar nos testes de validação de formato.

## Fase 2: Otimização Guiada por Testes (LangSmith)

Cenário: O principal produto da SynapseTech é um Chatbot de Suporte ao Cliente. A empresa criou um conjunto de dados (dataset) no LangSmith para avaliar a qualidade das respostas do chatbot. Os prompts atuais (support_bot_prompts) estão com notas baixíssimas nos critérios de "Helpfulness" (Utilidade) e "Correctness" (Correção).

Requisitos (Fase 2):

Configuração: Configurar suas credenciais do LangSmith no projeto (conforme instruções no README.md do repositório base).

Execução: Rodar o script de avaliação (python run_langsmith_eval.py). Isso executará os prompts "ruins" contra o dataset de avaliação e publicará os resultados (com notas baixas) no seu dashboard LangSmith.

Iteração e Otimização: Sua tarefa é editar e refatorar os support_bot_prompts (no prompts.yml) iterativamente.

Meta de Qualidade: Você deve rodar o script de avaliação quantas vezes forem necessárias até que todos os prompts atinjam uma nota média mínima de 0.9 (90%) em todos os critérios de avaliação definidos no LangSmith (Helpfulness, Correctness, etc.).

Dicas:

Lembre-se da importância da especificidade, contexto e persona (Fase 1).

Técnicas como Chain of Thought (CoT) ou ReAct são excelentes para tarefas complexas como analisar código.

Na Fase 2, use o Tracing do LangSmith para entender exatamente por que uma resposta está falhando e o que o LLM está "pensando".

Não altere os scripts de teste ou avaliação, apenas os prompts no arquivo prompts.yml.

## Entrega:

O link do seu repositório GitHub (um fork do repositório base) com todo o código-fonte, incluindo o prompts.yml 100% preenchido e funcional.

Um README.md atualizado no seu repositório explicando:

Quais técnicas avançadas você escolheu para a Fase 1 e por quê.

Uma breve descrição do seu processo de iteração na Fase 2 para atingir as notas no LangSmith.

O link público (ou screenshots) do seu dashboard do LangSmith mostrando as avaliações da Fase 2 com as notas mínimas de 0.9 atingidas.