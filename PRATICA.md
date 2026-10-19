# Prática: um repo e uma mini app 🚀

Em **dupla ou trio** com quem está ao teu lado. Os repos criam-se no browser, o código envia-se pelo terminal.

> **Ainda não fizeste o setup?** Segue o [SETUP.md](SETUP.md) primeiro: Git, GitHub CLI e Claude.

No fim, o vosso grupo tem um repositório próprio no GitHub com uma mini app feita com o Claude, publicada num site. Cada mudança entrou por pull request.

> **Antes de começar:** decidam quem é a **Pessoa 1** (fica dona do repo), a **Pessoa 2** e, se forem trio, a **Pessoa 3**, e troquem os vossos usernames do GitHub.
>
> **Regra de ouro:** o Claude escreve, vocês revêem. Nada entra no `main` sem alguém do grupo ler o pull request.

---

## Passo 1 — Criar o repo (~8 min)

### Pessoa 1

1. No GitHub: **+ → New repository**.
   - Nome: `o-nosso-repo` (sem espaços)
   - **Public**
   - ✅ **Add a README file**
   - **Create repository**
2. **Settings → Pages**. Em *Build and deployment*: Source **Deploy from a branch**, Branch **main**, pasta **/ (root)** → **Save**.
3. **Settings → Collaborators → Add people** e convida a Pessoa 2 (e a 3).
4. **Settings → Rules → Rulesets → New branch ruleset**:
   - Nome: `proteger-main` · Enforcement status: **Active**
   - Target branches: **Add target → Include default branch**
   - ✅ **Require a pull request before merging** → Required approvals: **1**
   - **Create**

### Pessoas 2 e 3, ao mesmo tempo

1. Aceitem o convite: chega por email, ou abram `https://github.com/<username-da-pessoa-1>/o-nosso-repo/invitations`.
2. Se ainda não o fizeram no [SETUP.md](SETUP.md), preparem o Claude, que é preciso no Passo 2:
   - Em [claude.ai](https://claude.ai), **Settings → Capabilities** → liguem **Code execution and file creation**.
   - Descarreguem [`skills/junitec-mini-app.zip`](skills/junitec-mini-app.zip) deste guia.
   - **Customize → Skills → + → Upload a skill** e escolham o zip.

---

## Passo 2 — Gerar a app com o Claude (~12 min)

Escolham **uma** ideia, ou inventem outra útil para um projecto de consultoria ou inovação:

| # | Mini app | Para quê |
|---|---|---|
| 1 | **Calculadora de orçamento** | Horas × perfil × taxa, com o total do projecto |
| 2 | **Matriz impacto × esforço** | Pôr ideias num 2×2 e ver quais fazer primeiro |
| 3 | **Diagnóstico digital de PME** | Quiz com uma pontuação e recomendações |
| 4 | **TAM / SAM / SOM** | Estimar o mercado de uma ideia em três números |
| 5 | **Temporizador de pitch** | 3 minutos, com avisos aos 2:00 e aos 2:45 |
| 6 | **Votação de ideias** | Juntar ideias de um brainstorm e votar nas melhores |
| 7 | **Proposta de valor** | Canvas preenchível que se exporta em texto |

Numa conversa nova, escrevam um pedido com três partes: **o quê**, **para quem** e **o que faz**.

```
Usa a skill junitec-mini-app.
Faz uma [calculadora de orçamento] para [consultores da JUNITEC que
preparam propostas a PME]. Deve permitir [acrescentar perfis com horas
e taxa à hora e ver o total com e sem IVA].
```

1. Testem a app no próprio Claude (abre ao lado da conversa).
2. Peçam **duas melhorias**, uma de cada vez. Por exemplo: "acrescenta exportar CSV" ou "o total tem de ficar maior".
3. Copiem o código completo do `index.html`, do `<!doctype html>` ao `</html>`.

💡 Um condutor por grupo. Se a conta dele chegar ao limite de mensagens, passem para a de um colega e colem o último código.

---

## Passo 3 — Publicar por pull request (~10 min)

Quem tem o código do Passo 2 faz isto no terminal (no Windows, no **Git Bash**). Os outros acompanham ao lado.

1. Copiar o repo do grupo para o computador e criar um branch:

   ```
   git clone https://github.com/<username-da-pessoa-1>/o-nosso-repo.git
   cd o-nosso-repo
   git switch -c adiciona-app
   ```

2. Guardem o código do Claude como **`index.html`** dentro da pasta `o-nosso-repo`. Podem descarregar o ficheiro no Claude ou colar o código num editor e fazer *Guardar como*.

3. Ver, guardar e enviar:

   ```
   git status
   git add index.html
   git commit -m "Adiciona a mini app"
   git push -u origin adiciona-app
   ```

4. O `git push` mostra um link. Abram-no → **Create pull request**. Em **Reviewers**, à direita, peçam revisão a um colega do grupo.
5. 👀 **Quem revê:** separador **Files changed** → **Review changes** → *Approve* → *Submit review*.
6. **Merge pull request → Confirm merge → Delete branch**.
7. Abram `https://<username-da-pessoa-1>.github.io/o-nosso-repo/` (cerca de 1 minuto depois do merge). 🎉

> **Sem terminal?** No repo do grupo: **Add file → Create new file**, nome `index.html`, colem o código → **Commit changes… → Create a new branch for this commit and start a pull request**. Depois sigam do ponto 4.

---

## Passo 4 — Uma melhoria com issue (~8 min)

1. Escolham uma das melhorias que o Claude sugeriu e criem uma **issue** com ela (**Issues → New issue**), atribuída a alguém do grupo em **Assignees**. Reparem no número (ex.: `#1`).
2. Essa pessoa dá ao Claude o código **actual**: abre o `index.html` no GitHub, copia-o e cola-o na conversa. Pede a melhoria e revê o que mudou.
3. No terminal, dentro da pasta `o-nosso-repo`:

   ```
   git switch main
   git pull
   git switch -c melhoria-1
   ```

4. Substituam o conteúdo do `index.html` pelo código novo e guardem.

   ```
   git diff
   git add index.html
   git commit -m "Acrescenta exportar CSV"
   git push -u origin melhoria-1
   ```

5. Abram o link → **Create pull request** → na descrição escrevam `Closes #1`.
6. Review de um colega → merge. A issue **fecha-se sozinha** e o site actualiza-se.

> **Se não foste tu a fazer o Passo 3**, começa por `git clone …` e `cd o-nosso-repo`, como no Passo 3, e depois segue daqui.

---

## Bónus — Um conflito de propósito

1. Duas pessoas editam ao mesmo tempo o **título** da app no `index.html`, cada uma com um nome diferente e cada uma no seu branch e pull request.
2. O primeiro pull request entra. O segundo mostra ⚠️ *This branch has conflicts*. Cliquem em **Resolve conflicts**.
3. Decidam juntos a versão final, apaguem as linhas `<<<<<<<`, `=======` e `>>>>>>>` e façam **Mark as resolved → Commit merge**.

## Se o terminal der erro

| Mensagem | O que fazer |
|---|---|
| `fatal: not a git repository` | Faltou o `cd o-nosso-repo`. |
| `Permission denied` ou `403` no push | Ainda não aceitaste o convite do repo, ou falta o `gh auth login` do [SETUP.md](SETUP.md). |
| `protected branch` ou `rejected` | Tentaste enviar para o `main`. Cria um branch com `git switch -c …`. |
| `Author identity unknown` | Falta o `git config --global user.name/email` do [SETUP.md](SETUP.md). |
| `nothing to commit` | O `index.html` não foi guardado dentro da pasta `o-nosso-repo`. |

---

## Boas práticas

- **Revê sempre.** O Claude erra com confiança: testem cada botão e cada cálculo.
- **Dados de clientes ficam fora.** Nada confidencial numa conta pessoal.
- **Nada de chaves de API nem passwords**, nem no código nem no chat.
- **Pequenos passos.** Um pedido, uma mudança, um pull request.
