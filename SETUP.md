# Setup antes da formação ⚙️

Faz isto **antes da formação de hoje, segunda-feira, 19/10, às 18h**. Demora 10 a 15 minutos. Se alguma coisa falhar, escreve no canal do Slack da formação: a tua dúvida pode ser a de outra pessoa. Se não der para resolver por aí, resolvemos na sala.

Precisas de quatro coisas:

1. Uma conta GitHub
2. O Git e o GitHub CLI instalados
3. O Git ligado à tua conta GitHub
4. O Claude preparado

---

## 1. Conta GitHub

Cria a conta em [github.com/signup](https://github.com/signup) e **confirma o email**. Sem o email confirmado não consegues criar repositórios.

---

## 2. Instalar o Git e o GitHub CLI

O **Git** guarda as versões do código. O **GitHub CLI** (`gh`) liga o teu computador à tua conta GitHub sem precisares de passwords nem tokens.

### Windows

**Opção A, pelo terminal.** Abre o **PowerShell** e corre:

```
winget install --id Git.Git -e --source winget
winget install --id GitHub.cli -e --source winget
```

**Opção B, com instaladores.** Descarrega e instala com as opções por omissão:
- Git: [git-scm.com/download/win](https://git-scm.com/download/win)
- GitHub CLI: [cli.github.com](https://cli.github.com)

Depois **fecha o terminal e abre o Git Bash** (procura "Git Bash" no menu Iniciar). Usa sempre o Git Bash na formação: os comandos são iguais aos do Mac e do Linux.

### macOS

Abre o **Terminal** (Cmd + Espaço → "Terminal").

1. Escreve `git --version`. Se aparecer uma janela a pedir as *Command Line Tools*, carrega em **Instalar** e espera que acabe.
2. Para o GitHub CLI:
   - Se usas Homebrew: `brew install gh`
   - Se não sabes o que é Homebrew: descarrega o instalador para macOS em [cli.github.com](https://cli.github.com)

### Linux

| Distribuição | Comando |
|---|---|
| Ubuntu / Debian | `sudo apt update && sudo apt install git gh` |
| Fedora | `sudo dnf install git gh` |
| Arch | `sudo pacman -S git github-cli` |

Se o `gh` não existir na tua versão, segue as instruções em [cli.github.com](https://cli.github.com).

---

## 3. Ligar o Git à tua conta GitHub

No terminal (Git Bash no Windows), corre:

```
gh auth login
```

Responde assim:

| Pergunta | Resposta |
|---|---|
| Where do you use GitHub? | **GitHub.com** |
| Preferred protocol for Git operations? | **HTTPS** |
| Authenticate Git with your GitHub credentials? | **Yes** |
| How would you like to authenticate? | **Login with a web browser** |

Copia o código de 8 caracteres que aparece, carrega em Enter, cola-o no browser e autoriza.

Depois diz ao Git quem és. Usa o **mesmo email da conta GitHub**:

```
git config --global user.name "O Teu Nome"
git config --global user.email "o-teu-email@exemplo.com"
```

---

## 4. Preparar o Claude

1. Cria conta em [claude.ai](https://claude.ai). A conta grátis chega. Podes usar o browser ou a app Claude Desktop: é a mesma conta e as mesmas skills.
2. **Settings → Capabilities** → liga **Code execution and file creation**.
3. Descarrega a skill [`skills/junitec-mini-app.zip`](skills/junitec-mini-app.zip) deste repo (abre o ficheiro → botão de download).
4. No Claude: **Customize → Skills → + → Upload a skill** → escolhe o zip.

---

## ✅ Confirma que está tudo bem

Corre estes três comandos:

```
git --version
gh auth status
git clone https://github.com/RomyDevv/github-lab.git
```

Está tudo bem se:
- o primeiro mostra uma versão (ex.: `git version 2.47.0`);
- o segundo diz **Logged in to github.com account <o-teu-username>**;
- o terceiro cria uma pasta `github-lab`. Podes apagá-la depois.

No Claude, a skill **junitec-mini-app** aparece em **Customize → Skills**.

**Opcional, mas ajuda:** um editor de código como o [VS Code](https://code.visualstudio.com), para abrir e guardar o `index.html`. Também dá com o Bloco de Notas ou o TextEdit.

---

## Se der erro

| Erro | O que fazer |
|---|---|
| `git: command not found` ou `'git' is not recognized` | Fecha e volta a abrir o terminal. Se continuar, repete a instalação. |
| `gh: command not found` | O mesmo: reabre o terminal; no Windows usa o Git Bash. |
| O browser não abre no `gh auth login` | Abre à mão [github.com/login/device](https://github.com/login/device) e cola o código. |
| Pede password num `git push` | O `gh auth login` não ficou feito. Corre-o outra vez e responde **Yes** à pergunta sobre o Git. |
| Não aparece *Capabilities* ou *Skills* no Claude | Actualiza a página. Se continuar, escreve no canal do Slack. |
