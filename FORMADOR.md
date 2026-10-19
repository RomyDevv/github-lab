# Preparação (só para o formador)

Os participantes não precisam de acesso a este repo: só o lêem.

## 1. Pedir aos participantes

- Conta em [github.com](https://github.com/signup) com o **email confirmado** (sem isso não se criam repos).
- Conta em [claude.ai](https://claude.ai) (a gratuita serve).
- Portátil com bateria.

## 2. Publicar o guia

```bash
# dentro desta pasta
git init -b main
git add .
git commit -m "Guia da formação Git, GitHub e Claude"
gh repo create github-lab --public --source . --push
```

Tem de ser **público** para todos o poderem ler sem convite.

## 3. Ensaio (na véspera)

Com uma segunda conta (ou com um colega), faz a prática toda do `PRATICA.md`:

- o site abre em `https://<username>.github.io/<repo>/` depois do merge;
- o ruleset bloqueia um merge sem aprovação;
- numa conta **gratuita** do Claude, a skill carrega e gera a app; vê também se aparece **+ → Add from GitHub**;
- os nomes dos botões no GitHub e no Claude batem certo com o guia.

## 4. Demo de Claude Code

Num repo de teste com um `index.html`, deixa pronto o pedido: «Acrescenta modo escuro à app. Cria um branch e abre um pull request.»

## Problemas comuns

| Sintoma | Causa | Solução |
| --- | --- | --- |
| Não consegue criar repo | Email da conta por confirmar | Confirmar o email e recarregar |
| A Pessoa 2 não vê o ✏️ no ficheiro do grupo | Convite por aceitar | `github.com/<pessoa-1>/<repo>/invitations` |
| Site dá 404 | Ainda sem `index.html` no `main`, ou Pages a publicar | Fazer o merge do Passo 3; esperar ~1 min |
| Merge bloqueado | Falta aprovação (o ruleset está a funcionar) | Pedir review a um colega |
| A skill não aparece no Claude | Code execution desligado | Settings → Capabilities → ligar e carregar o zip outra vez |
| A app abre em branco | Código copiado a meio | Copiar do `<!doctype html>` ao `</html>` |
| Limite de mensagens do Claude | Conta gratuita | Passar para a conta de um colega |
