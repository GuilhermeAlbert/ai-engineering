# Como a IA Generativa Funciona

## Um modelo de linguagem prevê tokens

Um grande modelo de linguagem recebe uma sequência de tokens e estima qual token tende a vir em seguida. Repetida muitas vezes, essa operação produz respostas coerentes. O modelo pode explicar, resumir e programar porque aprendeu regularidades presentes em muitos exemplos, não porque consulta uma enciclopédia interna de fatos garantidos.

## Contexto e alucinação

A janela de contexto contém as instruções, documentos e partes relevantes da conversa disponíveis naquela execução. Quando faltam evidências, o modelo ainda pode produzir uma continuação plausível. É daí que surgem muitas alucinações: fluência sem sustentação. Sistemas sérios reduzem o risco com recuperação de fontes, ferramentas, restrições, avaliações e revisão humana proporcional ao impacto.

## RAG, ferramentas e agentes

RAG recupera trechos relevantes de uma fonte e os coloca no contexto antes da resposta. Ferramentas permitem consultar sistemas ou executar ações. Um agente combina o modelo com um ciclo de decisão: escolher uma ferramenta, observar o resultado e decidir o próximo passo. Cada camada aumenta capacidade e também amplia superfície de falha, permissões e necessidade de observabilidade.

## Custo e escolha de modelo

Modelos maiores nem sempre são a melhor opção. Qualidade suficiente, latência, privacidade, preço, janela de contexto, suporte a ferramentas e estabilidade operacional importam mais do que rankings genéricos. A escolha deve ser feita com casos representativos do próprio processo.

## Exercício

Monte dez casos reais, incluindo entradas ambíguas e adversariais. Compare dois modelos usando o mesmo critério de qualidade, custo, tempo e taxa de intervenção humana.

---

[← Anterior: Modelos e Comportamento do Sistema](./README.md) · [Voltar a Modelos](./README.md) · [Próximo: Engenharia de Prompts →](../prompt-engineering/README.md)
