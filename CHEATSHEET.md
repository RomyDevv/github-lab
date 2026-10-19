# Cheatsheet de Git & GitHub

## Vocabulário

| Termo | Em português simples |
|---|---|
| **Repositório (repo)** | A pasta do projecto, com todo o histórico de alterações |
| **Commit** | Uma fotografia guardada do projecto, com uma mensagem a explicar o que mudou |
| **Branch** | Uma linha de trabalho paralela; mexes à vontade sem estragar o `main` |
| **`main`** | O branch principal — a versão "oficial" do projecto |
| **Pull Request (PR)** | Um pedido para juntar o teu branch ao `main`, com discussão e revisão |
| **Merge** | Juntar as alterações de um branch noutro |
| **Conflito** | Duas pessoas mudaram a mesma linha; um humano tem de decidir |
| **Clone** | Copiar um repo do GitHub para o teu computador |
| **Push / Pull** | Enviar commits para o GitHub / trazer commits do GitHub |
| **Issue** | Uma tarefa, bug ou ideia, com discussão e responsável |
| **Actions** | Automatismos que correm sozinhos (testes, deploys…) |

## Os comandos do dia-a-dia

```bash
git clone <url>                 # copiar o repo para o computador
git switch main && git pull     # actualizar antes de começar
git switch -c nome-do-branch    # criar um branch novo
git status                      # o que mudou?
git diff                        # ver as mudanças linha a linha
git add <ficheiro>              # preparar para commit (ou: git add .)
git commit -m "Mensagem clara"  # guardar a fotografia
git push -u origin nome-do-branch  # enviar para o GitHub (1.ª vez)
git push                        # enviar (seguintes)
git log --oneline               # histórico resumido
```

## Ups, enganei-me

```bash
git restore <ficheiro>          # deitar fora alterações não guardadas num ficheiro
git restore --staged <ficheiro> # tirar do "add" sem perder as alterações
git commit --amend -m "Nova msg"  # corrigir a mensagem do último commit (antes do push)
```

## Boas práticas para os vossos projectos

- **Nunca** façam commit de passwords, chaves de API ou ficheiros `.env`. Usem um `.gitignore`.
- PRs pequenos, com uma mudança cada. São mais rápidos de rever.
- Mensagens de commit no imperativo: "Adiciona login", "Corrige cálculo do IVA".
- Protejam o `main` (Settings → Rules): obriguem a PR e a pelo menos uma revisão.
- Um bom `README.md` responde a: o que é isto, como corro, como contribuo.
- Usem Issues + Projects para saber quem está a fazer o quê — mesmo quem não programa.
