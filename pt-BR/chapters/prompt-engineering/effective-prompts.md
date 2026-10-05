# Projetando Prompts Eficazes

## De pedido a especificação

Um bom prompt define objetivo, contexto, público, restrições, dados disponíveis, formato de saída e critérios de qualidade. Pedir “faça um relatório” transfere decisões demais para o modelo. Informar o público, as fontes permitidas, a estrutura e o limite de palavras torna o resultado mais consistente e mais fácil de avaliar.

Zero-shot fornece apenas a instrução. Few-shot inclui exemplos. Atribuir um papel pode orientar vocabulário e perspectiva, mas não concede competência real. Para problemas complexos, decomponha a tarefa em etapas verificáveis e peça evidências ou cálculos intermediários úteis, sem tratar qualquer explicação do modelo como prova de raciocínio verdadeiro.

## Templates e automação

Um template transforma um acerto casual em processo repetível. Separe campos variáveis da instrução permanente e versione mudanças. Em fluxos automatizados, valide entrada e saída, registre qual modelo e template foram usados e defina o que acontece quando a resposta não atende ao contrato.

```text
Objetivo: resumir as notas semanais.
Público: liderança da área.
Formato: Vitórias / Riscos / Próximas prioridades.
Limite: 150 palavras.
Regra: não invente fatos ausentes nas notas.
```

## Segurança

Não envie dados pessoais, segredos, código confidencial ou informações comerciais a uma ferramenta sem contrato, configuração e política adequados. O prompt faz parte da superfície de segurança; conteúdo externo pode tentar alterar instruções ou induzir ações indevidas.

## Exercício

Crie um template para o processo escolhido, teste cinco casos reais e registre os erros. Ajuste o prompt apenas quando a mudança melhorar casos representativos, não um exemplo isolado.

---

[← Anterior: Engenharia de Prompts](./README.md) · [Voltar a Engenharia de Prompts](./README.md) · [Próximo: IA na Organização →](../organization/README.md)
