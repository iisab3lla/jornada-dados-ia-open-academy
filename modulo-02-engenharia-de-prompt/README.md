# ❀ Engenharia de Prompt: criando prompts eficazes para IA Generativa 

Este curso faz parte da minha jornada na **Open Academy + Alura — Dados com IA**, focado em entender como estruturar prompts de forma estratégica para obter respostas mais precisas e úteis de modelos de IA generativa.

---

## ❀ Objetivo do Curso

Aprender como construir prompts eficazes utilizando técnicas modernas de engenharia de prompt, com foco em:
- Controle do comportamento do modelo
- Precisão nas respostas
- Reprodutibilidade de resultados
- Otimização de geração de texto

---

## ❀ Conteúdos Abordados

- Conceitos fundamentais de **LLMs** e proximidade semântica  
- Funcionamento de **tokens**  
- Engenharia de prompts: princípios básicos e avançados  
- Técnicas de **zero-shot**, **one-shot** e **few-shot prompting**  
- Métodos de **chain-of-thought** e **least-to-most** prompting  
- **Chain-of-verification** e **self-consistency** em prompts  

---

## ❀ Ferramentas Utilizadas

- ChatGPT  
- Outros modelos LLMs testados durante o curso

---

## ❀ Desafios Realizados

### ✿ Desafio 1 — Explorando probabilidades

**Objetivo:**  
Simular como o modelo escolhe palavras a partir de probabilidades.

**Atividade:**  
- Testar diversas frases incompletas  
- Analisar as palavras sugeridas e suas probabilidades  


**Resultado:**  

**Eu gosto de**

comer: 0.2
ler: 0.15
ouvir: 0.1
assistir: 0.08
fazer: 0.07

**Eu vou para**

casa: 0.3
escola: 0.2
trabalho: 0.15
lá: 0.1
cama: 0.08

**Eu estudo sobre**

história: 0.25
ciência: 0.2
matemática: 0.15
arte: 0.1
programação: 0.08


**O que aprendi:**  
- Como os modelos trabalham com distribuição de probabilidades  
- Como pequenas mudanças alteram a saída gerada  

---

### ✿ Desafio 2 — Princípios fundamentais de Engenharia de Prompt

**Objetivo:**  
Comparar resultados com e sem uso de boas práticas de engenharia de prompt.

**Experimento:**  
- Uso do jogo detetive (Coronel Mostarda)  
- Teste em versão simples e estruturada  
- Aplicação de subtarefas no prompt  

**Resultado:**  
(prompt com boas práticas)
Use as dicas a seguir para responder à seguinte questão de múltipla escolha, usando o seguinte procedimento:

(1) Primeiramente, analise as dicas uma por uma e considere se a dica é potencialmente relevante
(2) Em segundo lugar, combine as dicas relevantes para raciocinar a resposta correta à pergunta
(3) Em terceiro lugar, mapeie a resposta para uma das respostas de múltipla escolha: (a), (b) ou (c)

Dicas:

A Senhorita Scarlett era a única pessoa na sala.
A pessoa com o cachimbo estava na cozinha.
O Coronel Mostarda era a única pessoa no observatório.
O Professor Plum não estava na biblioteca nem na sala de bilhar.
A pessoa com o castiçal estava no observatório.
Pergunta: O Coronel Mostarda estava no observatório com o castiçal?
(a) Sim; O Coronel Mostarda estava no observatório com o castiçal
(b) Não; O Coronel Mostarda não estava no observatório com o castiçal
(c) Desconhecido, não há informações suficientes para determinar se o Coronel Mostarda estava no observatório com o castiçal

Resposta:

Análise das dicas:

"A Senhorita Scarlett era a única pessoa na sala."
→ Não menciona o Coronel Mostarda ou o observatório. Não relevante para a pergunta.

"A pessoa com o cachimbo estava na cozinha."
→ Não menciona o Coronel Mostarda ou o observatório. Não relevante para a pergunta.

"O Coronel Mostarda era a única pessoa no observatório."
→ Relevante: Confirma que o Coronel Mostarda estava no observatório.

"O Professor Plum não estava na biblioteca nem na sala de bilhar."
→ Não menciona o Coronel Mostarda ou o observatório. Não relevante para a pergunta.

"A pessoa com o castiçal estava no observatório."
→ Relevante: Confirma que o castiçal estava no observatório.

Combinação das dicas relevantes:

Dica 3: Coronel Mostarda estava no observatório.
Dica 5: O castiçal estava no observatório.

Vamos reavaliar as dicas com mais atenção para entender se o Coronel Mostarda estava com o castiçal no observatório:

Reanálise das dicas relevantes:

"O Coronel Mostarda era a única pessoa no observatório."
→ Isso significa que somente o Coronel Mostarda estava no observatório. Não havia mais ninguém lá.

"A pessoa com o castiçal estava no observatório."
→ Isso significa que alguém com o castiçal estava no observatório.

Combinação das informações:

Se somente o Coronel Mostarda estava no observatório (dica 3) e alguém com o castiçal estava no observatório (dica 5), então o Coronel Mostarda só pode ser a pessoa com o castiçal.

Mapeamento para as opções:
(a) Sim; O Coronel Mostarda estava no observatório com o castiçal.
→ Correta. Ele era a única pessoa no observatório, e o castiçal estava lá. Portanto, ele estava com o castiçal.
(b) Não; O Coronel Mostarda não estava no observatório com o castiçal.
→ Incorreta.
(c) Desconhecido, não há informações suficientes para determinar se o Coronel Mostarda estava no observatório com o castiçal.
→ Incorreta.

Resposta final:
(a) Sim; O Coronel Mostarda estava no observatório com o castiçal.


**O que aprendi:**  
- Como dividir tarefas melhora drasticamente a resposta  
- A importância da clareza na instrução  
- Como orientar o raciocínio do modelo  

---

### ✿ Desafio 3 — Comandos com exemplos (zero-shot, one-shot, few-shot)

**Objetivo:**  
Criar prompts usando exemplos para orientar o modelo.

**Atividade:**  
- Testar zero-shot prompting  
- Aplicar one-shot prompting  
- Criar exemplos para few-shot prompting  

**Resultado:**  
"Você é um modelo de linguagem que deve analisar o sentimento expresso em frases curtas.
Classifique cada frase como Positivo, Negativo ou Neutro, seguindo os exemplos abaixo:

"Adoro quando o suporte resolve meu problema rápido!"
Positivo

"O produto veio quebrado e ninguém responde meus e-mails."
Negativo

"Chegou no prazo, mas a embalagem estava rasgada."
Neutro

"O aplicativo melhorou muito depois da atualização."
Positivo

"Comprei pela terceira vez, e continuo amando!"
"Finalmente o site funcionou, depois de só três tentativas."

Positivo
Justificativa: expressão direta de satisfação e lealdade ("continuo amando") e repetição da compra reforça atitude positiva sem indicação de problema.

Neutro
Justificativa: contém emoção positiva (alívio/resultado: "funcionou") mas também indica frustração implícita pelo esforço necessário ("depois de só três tentativas"). Por combinar elementos positivos e negativos, enquadra-se como sentimento misto / neutro.


**O que aprendi:**  
- Few-shot é muito mais poderoso que apenas instruções  
- Exemplos funcionam como “treino contextual” para o modelo  
- A qualidade do exemplo impacta diretamente na qualidade da resposta  

---

### ✿ Desafio 4 — Cadeia de pensamentos (Chain-of-Thought)

**Objetivo:**  
Incentivar o modelo a resolver problemas usando raciocínio passo a passo.

**Atividades:**  
- Testes com problemas matemáticos  
- Uso de “explique passo a passo”  
- Comparação com prompts sem chain-of-thought  

**Resultado:**  
Pergunta: Tenho uma lista de pontuações obtidas por jogadores em um torneio. Quero calcular uma premiação equivalente a 10% da soma das pontuações dos jogadores que fizeram mais de 800 pontos.
Com base na lista abaixo, determine quantos jogadores ultrapassaram 800 pontos, quais foram suas pontuações, some esses valores e, por fim, calcule 10% do total obtido.

750
820
960
480
1020
895
630
870

Vamos resolver passo a passo:

Lista de pontuações:
750, 820, 960, 480, 1020, 895, 630, 870

1. Jogadores com mais de 800 pontos:

820

960

1020

895

870

✅ Total de jogadores acima de 800 pontos: 5

2. Soma dessas pontuações:

820 + 960 + 1020 + 895 + 870
= (820 + 960) = 1780
1780 + 1020 = 2800
2800 + 895 = 3695
3695 + 870 = 4565

✅ Soma total: 4565

3. Calcular 10% da soma:
10% de 4565 = 4565 × 0.10 = 456,50

✅ Resultado final:

Jogadores acima de 800 pontos: 5

Pontuações: 820, 960, 1020, 895, 870
Soma das pontuações: 4565
10% da soma: 456,50


**O que aprendi:**  
- A técnica melhora respostas em problemas lógicos  
- Modelos respondem melhor quando guiados pelo processo, não só pela resposta  

---

### ✿ Desafio 5 — Aplicação no cotidiano

**Objetivo:**  
Criar um prompt útil para o dia a dia.

**Possíveis temas:**  
- Organização de estudos    

**Resultado:**  

**Prompt criado**
Contexto:
Estou cursando Dados com IA pela Alura. 
Meu objetivo é utilizar esses conhecimentos para criar um portfólio atrativo para iniciar minha carreira em dados. 

Rotina atual: 
* Trabalho das 07:00 às 13:00 de segunda a sexta. 
* Das 19:00 às 22:00, faço faculdade (preciso dormir até as 23:00). 
* Nos fins de semana, reservo o tempo para meus familiares/hobbies (sem estudos). 

CRONOGRAMA DE AULAS ATE O FIM DO CURSO (aulas ao vivo - 8 horas) 
semana 1: IA generativa 
semana 2: Engenharia de prompt 
semana 3: Excel 
semana 4: Recursos visuais com excel 
semana 5: Excel: logica booleana 
semana 6: Excel: tabelas dinamicas 
semana 7: Power BI - dashboard 
semana 8: Power BI - ETL no Power Query 

Objetivos: 
Criar um plano de estudos detalhado e equilibrado para completar a formação em até 1 meses, considerando não apenas assistir às aulas, mas também: 

* tempo para revisar conteúdos e as técnicas que posso utilizar; 
* realizar exercícios práticos e projetos de aplicação (me ensinar como posso fazer isso de uma maneira efetiva, dando exemplos); 
* realizar curso fora as aulas ao vivos na plataforma da Alura (contem 10 cursos e são necessárias 76 horas para conclusão) 

Requisitos do plano: 
* Distribuir as horas de forma realista entre os dias úteis (segunda a sexta) 
* Incluir variedade de atividades: assistir às aulas, praticar, revisar e aplicar conceitos. 
* Apresentar o plano em formato de tabela semanal, com estimativa de tempo diário e meta de progresso. 

Tarefa do modelo: 
* Gere um plano de estudos semanal personalizado e um resumo das estratégias de estudo recomendadas, levando em conta minha rotina, meus horários e o objetivo de concluir o curso em até 1 meses. 
* Preciso que acompanhe o meu processo e ajuste o cronograma/estratégias de acordo com o meu desempenho.

**Dia	Horário	Atividade	Meta diária**
Segunda	17h – 19h	Aula ao vivo (tema da semana) + anotações principais	100% da aula da semana
Terça	17h – 19h	Revisão guiada + exercícios práticos sobre a aula ao vivo	Revisar 100% do conteúdo + aplicar 1 exercício
Quarta	17h – 19h	Curso complementar na Alura (relacionado ao tema da semana)	Completar 1h30–2h do curso
Quinta	17h – 19h	Projeto prático curto (1 aplicação real do tema)	Criar ou aprimorar 1 parte do projeto
Sexta	17h – 19h	Revisão geral da semana + registro no portfólio (GitHub ou Notion)	Consolidar aprendizado e publicar resultados


**O que aprendi:**  
- Como adaptar engenharia de prompt para problemas reais  
- Como refinar prompts por tentativa e erro  
- Como transformar IA em uma ferramenta prática do cotidiano  

---

## ❀ Principais Aprendizados do Curso

- Engenharia de prompt é essencial para extrair o máximo dos LLMs  
- Clareza e estrutura fazem total diferença  
- Modelos respondem melhor com contexto bem definido  
- Bons prompts são iterativos, não surgem perfeitos  

---

## ❀ Conclusão

Este curso me permitiu aprofundar meu controle sobre modelos de IA generativa, transformando a IA de uma ferramenta genérica para uma ferramenta precisa, moldada para minhas necessidades reais.

