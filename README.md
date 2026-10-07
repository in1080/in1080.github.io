# IN1080 - Tópicos Avançados em Linguagens de Programação 3 - Análise de Programas

## Programa de Pós-Graduação em Ciência da Computação, [Centro de Informática](http://www.cin.ufpe.br), ([UFPE](http://www.ufpe.br))

### Instrutor

* **Professor:** Leopoldo Motta Teixeira ([@leopoldomt](https://github.com/leopoldomt) --- lmt@cin)

### Horário de Aulas

* Segunda (15h-17h), Sala E331
* Quarta (13h-15h), Sala E331 

### Ementa

Esta disciplina cobre os fundamentos e a prática da análise automática de programas, uma das áreas centrais da Engenharia de Software e da teoria das linguagens de programação. Partindo de semântica operacional e representações intermediárias, o curso desenvolve progressivamente as principais famílias de técnicas: análise de fluxo de dados e interpretação abstrata, análise interprocedural e de ponteiros, arcabouços distribuídos (IFDS/IDE), análise dinâmica e instrumentação, execução simbólica e geração de testes, além de tópicos avançados como fuzzing e análise neuro-simbólica. A abordagem combina aulas teóricas expositivas, laboratórios práticos com ferramentas reais e sessões de discussão de artigos seminais e recentes, culminando em um projeto conduzido pelos alunos.

### Objetivos de Aprendizagem

Ao concluir a disciplina, o aluno será capaz de:

- Formalizar a semântica de linguagens imperativas simples e raciocinar sobre execuções de programas.
- Projetar e implementar análises de fluxo de dados em um arcabouço de reticulados, provando terminação e correção.
- Aplicar a teoria de interpretação abstrata para derivar e justificar análises estáticas.
- Construir análises interprocedurais sensíveis ao contexto e análises de ponteiros.
- Trabalhar dentro de arcabouços reais de análise (tree-sitter, Checker Framework, SootUp/Heros) em vez de reimplementar tudo do zero.
- Implementar análise dinâmica via instrumentação.
- Usar SMT, execução simbólica e concolic testing.
- Avaliar criticamente trabalhos de pesquisa da área.
- Desenvolver e apresentar um projeto de análise de programas.

### Bibliografia Sugerida

- Aldrich, J., Le Goues, C. & Padhye, R. — [*Program Analysis*](https://cmu-program-analysis.github.io/2025/). CMU, 2025.
    - referenciado como CMU-PA no plano de ensino abaixo.
- Møller, A. & Schwartzbach, M. I. — [*Static Program Analysis*](https://cs.au.dk/~amoeller/spa/). Aarhus, 2025.
    - referenciado como SPA no plano de ensino abaixo. 
- Rival, X. & Yi, K. — *Introduction to Static Analysis: An Abstract Interpretation Perspective*. MIT Press, 2020.

### Linguagens e Ferramentas

**Linguagem de referência (teoria, quadro):** WHILE / WHILE₃ADDR (CMU-PA).

**Ferramentas a serem usadas no eixo prático**:

| Ferramenta | Linguagem | Papel |
|---|---|---|
| [tree-sitter](https://tree-sitter.github.io/) | Python (bindings) | Representação de programas (AST) |
| [Checker Framework](https://checkerframework.org/) | Java | *Dataflow Framework* |
| [SootUp](https://soot-oss.github.io/SootUp/) | Java | Análise de bytecode: pontos-to, call graphs |
| [Heros](https://github.com/soot-oss/heros) | Java | Solver IFDS/IDE genérico, plugável ao SootUp |
| [DynaPyt](https://github.com/sola-st/DynaPyt) | Python | Instrumentação dinâmica e taint tracking |
| [Z3](https://github.com/Z3Prover/z3) (`z3-solver`) | Python | SMT e verificação de propriedades |

### Metodologia

As sessões seguem quatro formatos:

* **Teórica:** aula expositiva.
* **Discussão de artigo:** leitura obrigatória prévia, cada aluno traz pelo menos uma pergunta para a discussão.
* **Laboratório:** atividade prática com uma das ferramentas.
* **Projeto:** acompanhamento, orientação e apresentações do projeto conduzido pelos alunos.

Cada unidade é estruturada para responder, de forma explícita, a três perguntas que norteiam nossos estudos na área:

1. Qual é a semântica de referência?
2. Que aproximação está sendo feita sobre essa semântica?
3. Qual é o trade-off de custo, precisão e completude da aproximação?

### Avaliação

| Componente | Peso | Descrição |
|---|---|---|
| Participação | 40% | Presença e engajamento nas sessões de discussão de artigos |
| Projeto | 60% | Proposta (sem nota) + relatório intermediário + apresentação final + relatório final. (Individual) |

**Marcos do projeto:**

| Data | Marco |
|---|---|
| 24/10 | Entrega da proposta (PDF, 1–2 páginas) |
| 26/10 | Apresentação de propostas em aula |
| 11/11 | Entrega do relatório intermediário (PDF, 4–6 páginas) |
| 14/12 e 16/12 | Apresentações finais |
| 21/12 | Prazo final para entrega do relatório e repositório do projeto (sem aula) |

### Plano de Ensino

*Este plano de ensino está sujeito a alterações durante o semestre. Visite frequentemente a página para obter a versão mais atualizada ou acompanhe as atualizações no repositório.*

| Data     | Dia da Semana | Horário   | Conteúdo Programático | Atividades Associadas |
| -------- | ------------- | --------- | --------------------- | ---------------------- |
| 17.08.26 | segunda       | 15h–17h   | Apresentação do curso | Leitura opcional para contexto: CMU-PA Cap. 1 |
| 19.08.26 | quarta        | 13h–15h   | Discussão: Hoare — The Emperor's Old Clothes (CACM 1981, Turing Award Lecture 1980) | Leitura obrigatória; trazer 1 pergunta para o debate |
| 24.08.26 | segunda       | 15h–17h   | Representação de programas: AST, CFG, semântica operacional | Leitura: CMU-PA Cap. 2 |
| 26.08.26 | quarta        | 13h–15h   | [Discussão: interpretação abstrata — a ideia central](https://www.di.ens.fr/~cousot/AI/) | Leitura obrigatória: [Cousot, *Abstract Interpretation* (ACM Comput. Surv. 28(2), 1996)](https://dl.acm.org/doi/10.1145/234528.234740). Opcional para aprofundar: Cousot & Cousot [POPL'77](https://dl.acm.org/doi/10.1145/512950.512973) + [POPL'79](https://dl.acm.org/doi/10.1145/567752.567778) |
| 31.08.26 | segunda       | 15h–17h   | Laboratório: tree-sitter | tree-sitter (Python) instalado |
| 02.09.26 | quarta        | 13h–15h   | Análise de tipos | Leitura complementar opcional: SPA Cap. 3 |
| 07.09.26 | segunda       | 15h–17h   | **Independência do Brasil (Feriado Nacional)** | --- |
| 09.09.26 | quarta        | 13h–15h   | [REMOTA] Tópico a definir | Ler CMU-PA Caps. 4–5 antes da aula de 14/09 |
| 14.09.26 | segunda       | 15h–17h   | _Aula cancelada por motivo de saúde_ | --- |
| 16.09.26 | quarta        | 13h–15h   | Discussão: [Sadowski et al. — Lessons from Building Static Analysis Tools at Google (CACM 2018)](https://dl.acm.org/doi/10.1145/3188720) | Leitura obrigatória, trazer 1 pergunta |
| 21.09.26 | segunda       | 15h–17h   | Lattices, monotone framework, soundness | CMU-PA Caps. 4–5 |
| 23.09.26 | quarta        | 13h–15h   | Laboratório: Checker Framework | JDK + Maven/Gradle configurados. Leitura complementar opcional: [Papi et al., Practical Pluggable Types for Java (ISSTA 2008)](https://dl.acm.org/doi/10.1145/1390630.1390656) |
| 28.09.26 | segunda       | 15h–17h   | Análise interprocedural | Leitura: CMU-PA Caps. 8, 10 |
| 30.09.26 | quarta        | 13h–15h   | Discussão: [Distefano, Fähndrich, Logozzo & O'Hearn — Scaling Static Analyses at Facebook (CACM 2019)](https://dl.acm.org/doi/10.1145/3338112) | Leitura obrigatória; trazer 1 pergunta |
| 05.10.26 | segunda       | 15h–17h   | Laboratório: SootUp | JDK + Maven/Gradle configurados. Leitura complementar opcional: [Karakaya et al., SootUp: A Redesign of the Soot Static Analysis Framework (TACAS 2024)](https://dl.acm.org/doi/10.1007/978-3-031-57246-3_13) |
| 07.10.26 | quarta        | 13h–15h   | IFDS | Leitura complementar opcional: SPA Cap. 9 |
| 12.10.26 | segunda       | 15h–17h   | **Nossa Senhora Aparecida (Feriado Nacional)** | --- |
| 14.10.26 | quarta        | 13h–15h   | Laboratório: Heros | JDK + Maven/Gradle configurados |
| 19.10.26 | segunda       | 15h–17h   | Discussão: [Eric Bodden, Inter-procedural data-flow analysis with IFDS/IDE and Soot (SOAP 2012)](https://dl.acm.org/doi/10.1145/2259051.2259052) | Leitura obrigatória; trazer 1 pergunta |
| 21.10.26 | quarta        | 13h–15h   | Análise dinâmica | --- |
| 26.10.26 | segunda       | 15h–17h   | Laboratório `dynapyt` | Python 3.10+ com `dynapyt` instalado. |
| 28.10.26 | quarta        | 13h–15h   | Discussão: [Michael Ernst — Static and dynamic analysis: synergy and duality (WODA 2003)](https://dl.acm.org/doi/10.1145/996821.996823) e [Eghbali and Pradel — DynaPyt: A Dynamic Analysis Framework for Python (FSE 2022)](https://dl.acm.org/doi/10.1145/3540250.3549126) | Leitura obrigatória; trazer 1 pergunta |
| 02.11.26 | segunda       | 15h–17h   | **Finados (Feriado Nacional)** | --- |
| 04.11.26 | quarta        | 13h–15h   | Apresentação de propostas de projeto (5-10 min) | Entrega da proposta (PDF, 1–2 páginas) até 24/10 |
| 09.11.26 | segunda       | 15h–17h   | Acompanhamento de projeto | Discutir estado atual do projeto |
| 11.11.26 | quarta        | 13h–15h   | Acompanhamento de projeto | Discutir estado atual do projeto |
| 16.11.26 | segunda       | 15h–17h   | Lógica de Hoare, SMT e execução simbólica | Leitura: CMU-PA Caps. 11–14. |
| 18.11.26 | quarta        | 13h–15h   | Laboratório: verificação de propriedades com Z3 (Python) | Python 3.10+ com `z3-solver` instalado |
| 23.11.26 | segunda       | 15h–17h   | Discussão: A definir | --- |
| 25.11.26 | quarta        | 13h–15h   | Geração de testes | Leitura: CMU-PA Cap. 16. Leitura complementar: [Manès et al., The Art, Science, and Engineering of Fuzzing: A Survey (IEEE TSE 2021)](https://ieeexplore.ieee.org/document/8863940) |
| 30.11.26 | segunda       | 15h–17h   | Acompanhamento de projeto | Discutir estado atual do projeto |
| 02.12.26 | quarta        | 13h–15h   | [REMOTA] A definir | --- |
| 07.12.26 | segunda       | 15h–17h   | Discussão: A definir | --- |
| 09.12.26 | quarta        | 13h–15h   | Acompanhamento de projeto | Discutir estado atual do projeto |
| 14.12.26 | segunda       | 15h–17h   | Apresentações finais de projeto — Parte 1 | Apresentações de 12–15 min |
| 16.12.26 | quarta        | 13h–15h   | Apresentações finais de projeto — Parte 2 | Apresentações de 12–15 min |
| 21.12.26 | segunda       | —         | **Prazo limite para entrega final do projeto (relatório + repositório)** | --- |
