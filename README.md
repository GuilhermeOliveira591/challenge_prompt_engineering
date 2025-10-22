# Desafio Final: O Otimizador de Prompts da SynapseTech

Parabéns! Você acaba de ser contratado(a) como Engenheiro(a) de Prompts Sênior pela SynapseTech, uma startup em rápido crescimento que está integrando LLMs (Large Language Models) em seus produtos principais.

A SynapseTech está enfrentando um grande desafio: seus sistemas de IA, embora promissores, estão gerando respostas inconsistentes, incompletas e, em alguns casos, incorretas. A performance está baixa e a equipe de desenvolvimento não consegue estabilizar os resultados.

Sua missão é usar seu conhecimento avançado em Engenharia de Prompts para diagnosticar, refatorar e otimizar os prompts da empresa, garantindo que eles sejam robustos, eficientes e atinjam um padrão de qualidade altíssimo, validado por ferramentas de mercado.

Objetivos: 

- Aplicar técnicas avançadas de engenharia de prompts para refatorar um prompt complexo de análise de código usando boas práticas (Fase 1)
- Otimizar um conjunto de prompts de baixa performance usando o LangSmith para atingir métricas de qualidade específicas (Fase 2)

# Repositórios úteis

[Curso de Prompt Engineering](https://github.com/devfullcycle/mba-ia-prompt-engineering/tree/main)

[Template básico com estrutura do projeto](https://github.com/GuilhermeOliveira591/challenge_prompt_engineering)


## Fase 1: Refatoração de Prompt Complexo (Análise de PR)
A equipe de DevOps da SynapseTech quer automatizar a criação de release notes. Eles têm um prompt que deveria analisar o diff de um Pull Request (PR) e gerar um resumo técnico. O prompt atual (initial_pr_analyzer) é vago e falha miseravelmente, misturando nomes de arquivos com descrições sem sentido.

Requisitos:

- Anaisar o prompt "ruim" fornecido no repositório base
- No arquivo prompts.yml, você deve criar um novo prompt (refined_pr_analyzer) que resolva o problema, refatorando o prompt ruim.
- Seu novo prompt deve utilizar pelo menos duas das técnicas avançadas vistas no curso (Ex: Tree of Thoughts, Skeleton of Thought Few-shot Learning) com exemplos claros, ou definição de Persona e Contexto muito bem estruturados.
- O repositório base contém testes automatizados (python run_tests.py --fase1). Seu prompt deve:

1. Estar corretamente formatado no prompts.yml.
2. Conter as variáveis de entrada esperadas (ex: pr_diff, pr_title).
3. Passar nos testes de validação de formato.

## Fase 2: Otimização Guiada por Testes (LangSmith)

O principal produto da SynapseTech é um Chatbot de Suporte ao Cliente. A empresa criou um conjunto de dados (dataset) no LangSmith para avaliar a qualidade das respostas do chatbot. Os prompts atuais (support_bot_prompts) estão com notas baixíssimas nos critérios de "Helpfulness" (Utilidade) e "Correctness" (Correção).

Requisitos:

- Configurar suas credenciais do LangSmith no projeto (conforme instruções no README.md do repositório base).
- Rodar o script de avaliação (python run_langsmith_eval.py). Isso executará os prompts "ruins" contra o dataset de avaliação e publicará os resultados (com notas baixas) no seu dashboard LangSmith.
- Sua tarefa é editar e refatorar os support_bot_prompts (no prompts.yml) iterativamente.
- Você deve rodar o script de avaliação quantas vezes forem necessárias até que todos os prompts atinjam uma nota média mínima de 0.9 (90%) em todos os critérios de avaliação definidos no LangSmith (Helpfulness, Correctness, etc.).

Dicas:

1. Lembre-se da importância da especificidade, contexto e persona (Fase 1).
2. Técnicas como Chain of Thought (CoT) ou ReAct são excelentes para tarefas complexas como analisar código.
3. Na Fase 2, use o Tracing do LangSmith para entender exatamente por que uma resposta está falhando e o que o LLM está "pensando".
4. Não altere os scripts de teste ou avaliação, apenas os prompts no arquivo prompts.yml.

## Entregável

- Realize primeiramente um fork do repositório base
- O link do seu repositório GitHub (um fork do repositório base) com todo o código-fonte, incluindo o prompts.yml 100% preenchido e funcional.
- Um README.md atualizado no seu repositório explicando, os seguintes itens:
1. Quais técnicas avançadas você escolheu para a Fase 1 e por quê
2. Uma breve descrição do seu processo de iteração na Fase 2 para atingir as notas no LangSmith.
3. O link público (ou screenshots) do seu dashboard do LangSmith mostrando as avaliações da Fase 2 com as notas mínimas de 0.9 atingidas.