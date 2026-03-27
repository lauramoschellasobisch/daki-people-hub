# People Intelligence Hub — Daki
## Como publicar o app (passo a passo para leigos)

---

### O que voce vai precisar
- Uma conta gratuita no GitHub (site para guardar o codigo)
- Uma conta gratuita no Vercel (site que publica o app na internet)
- Sua chave de API da Anthropic (a mesma que usaria para acessar o Claude via API)

Tempo estimado: 20–30 minutos na primeira vez.

---

## PASSO 1 — Criar conta no GitHub

1. Acesse **github.com**
2. Clique em **Sign up** (canto superior direito)
3. Preencha email, senha e username (pode ser qualquer nome)
4. Confirme o email que eles enviam
5. Conta criada! ✓

---

## PASSO 2 — Criar repositorio e subir os arquivos

1. No GitHub, clique no botao **+** (canto superior direito) → **New repository**
2. Em **Repository name**, escreva: `daki-people-hub`
3. Deixe marcado como **Private** (privado — so voce ve)
4. Clique em **Create repository**

Agora vamos subir os arquivos. A forma mais simples e pelo site:

5. Dentro do repositorio criado, clique em **uploading an existing file** (link no meio da pagina)
6. Arraste os seguintes arquivos/pastas para a area de upload:
   - `package.json`
   - `vercel.json`
   - A pasta `api/` (com o arquivo `analyze.js` dentro)
   - A pasta `public/` (com o arquivo `index.html` dentro)
7. Em baixo da pagina, clique em **Commit changes** (botao verde)

Seus arquivos estao no GitHub! ✓

---

## PASSO 3 — Criar conta no Vercel e conectar ao GitHub

1. Acesse **vercel.com**
2. Clique em **Sign Up**
3. Escolha **Continue with GitHub** — isso conecta os dois automaticamente
4. Autorize o Vercel a acessar seu GitHub (clique em Authorize)
5. Conta criada e conectada! ✓

---

## PASSO 4 — Publicar o app

1. No Vercel, voce vera sua tela inicial. Clique em **Add New → Project**
2. Na lista de repositorios do GitHub, encontre **daki-people-hub** e clique em **Import**
3. Na tela de configuracao, deixe tudo como esta (nao precisa mudar nada)
4. Clique em **Deploy**
5. Aguarde 1–2 minutos. O Vercel vai publicar o app automaticamente!

Quando terminar, aparece uma tela com confetes e um link tipo:
`https://daki-people-hub.vercel.app`

---

## PASSO 5 — Adicionar a chave de API (OBRIGATORIO para a IA funcionar)

Sem esse passo, o botao "Analisar" nao vai funcionar.

1. No Vercel, va ate o seu projeto **daki-people-hub**
2. Clique na aba **Settings** (no menu do projeto)
3. No menu lateral, clique em **Environment Variables**
4. Clique em **Add New**
5. Em **Key**, escreva exatamente: `ANTHROPIC_API_KEY`
6. Em **Value**, cole sua chave de API da Anthropic (comeca com `sk-ant-...`)
7. Clique em **Save**

Agora va em **Deployments** → clique nos tres pontinhos do ultimo deploy → **Redeploy**

Aguarde 1 minuto e pronto! ✓

---

## PASSO 6 — Acessar e usar o app

1. Volte para a pagina inicial do projeto no Vercel
2. Clique no link do seu site (ex: `https://daki-people-hub.vercel.app`)
3. O hub vai abrir no navegador!

**Voce pode acessar esse link de qualquer lugar** — computador, celular, qualquer navegador.
**Ninguem mais consegue acessar** (a menos que voce compartilhe o link).

---

## Duvidas frequentes

**Onde encontro minha chave de API da Anthropic?**
Acesse console.anthropic.com → API Keys → Create Key

**O app vai custar alguma coisa?**
O Vercel e gratuito para uso pessoal. O GitHub tambem. Voce paga apenas pelo uso da API da Anthropic (por numero de tokens processados — em uso leve, custa centavos por mes).

**Posso atualizar os arquivos depois?**
Sim! So substituir os arquivos no GitHub e o Vercel atualiza automaticamente em 1–2 minutos.

**O app e seguro? Meus dados ficam salvos?**
Os dados ficam apenas no seu navegador (nao ha banco de dados). Cada vez que fechar e abrir o app, o historico reinicia. Se quiser persistencia, podemos adicionar isso depois.

**Esqueci o link do meu app**
Acesse vercel.com → seu projeto → o link esta na pagina principal do projeto.
