---
name: junitec-mini-app
description: Usa sempre que alguém pedir uma mini app, ferramenta, calculadora, quiz, dashboard ou protótipo web para um projecto de consultoria ou inovação da JUNITEC. Gera uma app num único ficheiro index.html, no estilo visual da JUNITEC, pronta a publicar com GitHub Pages.
---

# Mini apps JUNITEC

Gera mini apps web para projectos de consultoria e inovação, prontas a pôr num repositório GitHub e a publicar com GitHub Pages.

## Formato da entrega

- **Um único ficheiro chamado `index.html`.** HTML, CSS e JavaScript no mesmo ficheiro.
- **Sem dependências externas**, excepto a fonte Montserrat do Google Fonts:
  `<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">`
- **Sem servidor, sem base de dados e sem chaves de API.** Se a app precisar de guardar dados, usa `localStorage` e explica isso na própria app.
- Mostra a app como artefacto, para se poder testar logo, e entrega o código completo, nunca excertos.
- Funciona em telemóvel: layout em coluna abaixo de 640px.

## Estilo visual

| Uso | Cor |
|---|---|
| Fundo principal | `#175FAA` |
| Cartões e áreas de trabalho | `#F6F6F6`, com texto `#3D4F6B` e títulos `#175FAA` |
| Destaques, botões, números | `#74D1EF` (texto escuro `#0944A1` por cima) |
| Texto sobre azul | `#F6F6F6` e `#E2EEFF` |
| Filetes | `#4D85C2` sobre azul, `#C9DAEE` sobre claro |

- Fonte: só Montserrat. Título a 700, corpo a 400.
- Por baixo do título vai uma barra `#74D1EF` com 120×6px e cantos arredondados.
- Botões com `border-radius:8px` e sem sombras.
- No rodapé: "Feito pela JUNITEC" a 12px, cor `#E2EEFF`.

## Conteúdo

- Escreve a interface em português de Portugal, com frases curtas.
- No topo, uma frase diz para que serve a app e para quem é.
- Mostra um exemplo já preenchido, para a app nunca abrir vazia.
- Quando houver um resultado (total, pontuação, prioridade), destaca-o em grande, em `#74D1EF`.
- Põe um botão "Copiar resultado" ou "Exportar CSV" quando fizer sentido para levar o resultado para um relatório.
- Nunca inventes dados reais de clientes, empresas ou mercados. Usa valores de exemplo claramente marcados como tal.

## Código

- Comentários em português, curtos, a explicar cada bloco: estado, cálculo, interface.
- JavaScript simples, sem frameworks, com funções pequenas e nomes em português.
- No fim da resposta, dá 3 ideias de melhorias que o grupo pode pedir a seguir. Cada uma deve caber num pull request.

## Antes de entregar

- O ficheiro abre directamente no browser, sem erros na consola.
- Todos os botões fazem alguma coisa.
- O texto tem contraste suficiente: nada de texto claro sobre `#74D1EF`.
