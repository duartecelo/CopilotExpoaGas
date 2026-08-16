# Copiloto Expoagas

Copiloto de compras para a **43ª Convenção Gaúcha de Supermercados — Expoagas 2026**
(18 a 20 de agosto de 2026, Centro de Eventos da Fiergs, Porto Alegre).

**Aplicação publicada:** https://duartecelo.github.io/CopilotExpoaGas/

**Repositório:** https://github.com/duartecelo/CopilotExpoaGas

---

## O problema

Um comprador de supermercado chega na Fiergs com 610 expositores, 72 horas e nenhum
critério objetivo de decisão.

- É fisicamente impossível visitar 610 estandes em três dias. Na prática ele visita cerca de 40.
- A seleção desses 40 acaba definida por quem tem o estande maior ou o vendedor mais
  insistente, não por quem preenche a lacuna real do mix da loja.
- Ele volta com uma pasta de catálogos e, uma semana depois, não lembra qual proposta era de quem.
- O expositor pagou caro pelo espaço e não sabe quem passou nem por quê.

Decisão de compra de alto valor, tomada com informação ruim, com R$ 800 milhões em jogo.

## A solução

O Copiloto transforma a feira em um **roteiro com tese**. O comprador informa o perfil da
loja em poucos toques e recebe um plano de visita justificado: quem visitar, em que ordem,
por que aquele antes daquele e o que perguntar quando chegar lá.

### Os três núcleos

1. **Diagnóstico do mix.** Antes de sugerir qualquer estande, o app aponta onde a loja está
   descoberta, comparando o número de fornecedores por categoria com uma baseline por porte
   de operação. Entrega valor antes de qualquer visita.

2. **Casamento com lacunas e rota.** Cada expositor recebe um score calculado contra as
   lacunas identificadas naquele perfil. Um estande grande de bebidas fica fora do roteiro
   se a loja já tem bebida bem resolvida. A ordem de visita é otimizada pela posição física
   dos estandes na planta.

3. **Pauta de negociação.** Para cada estande, as perguntas que aquele comprador específico
   deveria fazer àquele fornecedor específico, derivadas das lacunas, do prazo médio, do
   pedido mínimo e da cobertura regional declarada.

### Por que não usar um assistente genérico

Um LLM genérico não sabe quem são os expositores desta edição nem onde cada um está na planta,
não conhece o mix da loja do usuário e não tem noção de posição física para otimizar rota.
A defesa do projeto é a combinação de **dado privado** (perfil da loja) com **dado do evento**
(expositores e planta) e **capacidade de agir**.

O matching e a rota são algoritmos determinísticos em JavaScript e não dependem de rede. Todo
o cálculo acontece no navegador, o que mantém a aplicação utilizável dentro do pavilhão, com
ou sem sinal.

## Temas estratégicos atacados

IA Generativa · Analytics · Gestão por indicadores · Supply Chain · Retail Media · Omnichannel

## Como executar

A aplicação é um arquivo único, sem backend e sem etapa de build.

```bash
git clone https://github.com/duartecelo/CopilotExpoaGas.git
```

Depois é só abrir `index.html` em qualquer navegador moderno, ou acessar a URL do GitHub Pages.

## Stack

- HTML5, CSS3 e JavaScript puro (ES6+), tudo em `index.html`
- SVG inline para a planta do pavilhão e a rota
- Sem framework, sem etapa de build, sem backend
- Única dependência externa: as famílias Zilla Slab e IBM Plex, servidas pelo Google Fonts.
  O carregamento usa `font-display: swap` e há pilha local de reserva, então a página
  continua legível e funcional sem rede, apenas com outra tipografia.

## Roteiro de demonstração

1. Escolher um dos três perfis prontos (mercado de bairro, rede regional, atacarejo).
2. Ler o diagnóstico de mix e as categorias marcadas como lacuna crítica.
3. Ver o roteiro desenhado sobre a planta, com os estandes numerados na ordem de visita.
4. Clicar em uma parada para abrir a pauta de negociação daquele fornecedor.
5. Mudar uma categoria no ajuste fino do mix e ver o roteiro inteiro se redesenhar,
   com estandes entrando e saindo.

## Sobre os dados

A lista nominal de expositores da Expoagas 2026 não é pública: fica restrita à Central do
Expositor da AGAS. Os expositores desta demonstração são, portanto, **simulados**, mas
construídos sobre informações reais do evento:

- a **taxonomia de setores** usada pela organização em 2026 (mercearia, bebidas, hortifrúti,
  açougue e perecíveis, padaria, bazar, equipamentos, tecnologia e serviços, higiene e limpeza);
- a **reorganização da feira por segmento** anunciada para esta edição, com empresas de
  setores semelhantes agrupadas em áreas contíguas;
- os **dois pavilhões**, incluindo a nova área climatizada de 7.000 m² que estreia em 2026.

Nomes e condições comerciais são fictícios e plausíveis para o mercado supermercadista gaúcho.

## Equipe

| Integrante | E-mail |
|---|---|
| Guilherme Perlasca | guilhermeperlasca@gmail.com |
| Fillipe Brito Pinto | britopintofillipe@gmail.com |
| Henrique Souza dos Santos | hss_2003@outlook.com |
| Daniel Chiaramonte | danieldeitoschiara@gmail.com |
| Marcelo Duarte de Aguiar | celo.duarte.2005@gmail.com |

---

Projeto desenvolvido durante o AppJam da Expoagas 2026.
