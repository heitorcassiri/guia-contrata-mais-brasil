# Guia do MEI · Contrata+Brasil

Guia interativo (conversa + passo a passo) para MEIs se cadastrarem no Contrata+Brasil.
Projeto de extensão universitária — ODS 8.

- Funciona no celular, sem login, sem coletar dados pessoais, sem IA.
- Abre sem internet depois da primeira visita.
- Todo o texto fica no `conteudo.json`.

## O que tem em cada arquivo

| Arquivo | Para que serve |
|---|---|
| `index.html` | O guia. Não precisa mexer. |
| `conteudo.json` | **Todos os textos**, links e configurações. É aqui que você edita. |
| `cartaz.html` | Cartaz A4 com QR code, para imprimir. |
| `sw.js` | Faz o guia abrir sem internet. Não precisa mexer. |
| `img/` | Coloque aqui os prints das telas (`passo-1.png` até `passo-7.png`). |
| `fontes.md` | De onde veio cada informação e quando foi conferida. |

---

## 1. Publicar no GitHub Pages (grátis)

Só precisa fazer uma vez.

1. Crie uma conta em **github.com** (grátis).
2. Toque em **"+" → "New repository"**. Nome: `guia-contrata-mais-brasil`. Marque **Public**. Clique em **Create repository**.
3. Na página do repositório, clique em **"uploading an existing file"**. Arraste **todos os arquivos e a pasta `img`** desta pasta. Clique em **Commit changes**.
4. Vá em **Settings → Pages**. Em **Branch**, escolha `main` e `/ (root)`. Clique em **Save**.
5. Espere 1 a 2 minutos. O endereço vai ser:
   `https://SEU-USUARIO.github.io/guia-contrata-mais-brasil/`

> Alternativa sem conta no GitHub: **app.netlify.com/drop** — arraste a pasta inteira. Mas, para atualizar depois, você precisa ter conta no Netlify.

## 2. Configurar (no `conteudo.json`, bloco `"config"`)

```json
"config": {
  "dataConferencia": "24/11/2026",
  "urlGuia": "https://SEU-USUARIO.github.io/guia-contrata-mais-brasil/",
  "urlFormulario": "https://forms.gle/SEU-FORMULARIO",
  "whatsappInstituicao": "5511999999999",
  "nomeInstituicao": "Nome da instituição",
  ...
}
```

- **`urlGuia`**: o endereço publicado. É usado no **QR code do cartaz** e na mensagem de compartilhar.
- **`urlFormulario`**: link do Google Forms. Enquanto estiver vazio, o botão "Consegui me cadastrar!" aparece desativado.
- **`whatsappInstituicao`**: opcional. Só números, com 55 e DDD. Se ficar vazio, o botão "Falar com a instituição" não aparece.
- **`nomeInstituicao`**: aparece no topo do guia e no cartaz.
- **`dataConferencia`**: troque sempre que reconferir as informações.

### Formulário sugerido (Google Forms)
Em **Configurações**, deixe **desmarcado** "Coletar e-mails" (fica anônimo).
1. Primeiro nome (opcional) — resposta curta
2. Qual é a sua atividade? — resposta curta
3. Você concluiu o cadastro? — Sim / Não / Parei no meio (em qual etapa?)
4. O guia ajudou? — escala de 1 a 5

## 3. Editar textos

1. Abra o `conteudo.json` (no GitHub: clique no arquivo → ícone de lápis ✏️).
2. Mude **só o que está entre aspas** do lado direito. Exemplo:
   `"texto": "Seu texto aqui"`
3. Use `**negrito**` para negrito e `[texto](https://link)` para link.
4. Clique em **Commit changes**. Em 1–2 minutos o site atualiza.

⚠️ **Cuidado com aspas e vírgulas.** Se o arquivo quebrar, o guia mostra "Não consegui carregar o conteúdo". Para conferir, cole o conteúdo em um validador de JSON antes de salvar.

**Onde está cada coisa no `conteudo.json`:**
- `nos` → cada "fala" da conversa (o mesmo texto aparece no modo passo a passo). Cada uma tem `mensagens` e `botoes`.
- `etapas` → a ordem das etapas do modo passo a passo.
- `checklist`, `calculadora`, `certidoes` → os itens desses quadros.
- `intencoes` → palavras que a pessoa escreve e para onde a conversa vai (ex.: "senha" → ajuda da senha).
- `apelidos` → palavras do dia a dia para a busca de serviços (ex.: "bolo" → Confeiteiro).
- `naoAceitos` → serviços que **não** estão na lista (ex.: faxina).
- `ocupacoes` → a lista oficial (Anexo I dos Editais 03/2025 e 03/2026). Se o governo mudar a lista, atualize aqui.

> Quem visitou antes vê a versão nova a partir da **segunda** vez que abrir (por causa do modo sem internet). Isso é normal.

## 4. Prints das telas

Tire os prints **no celular**, com a sua conta, e salve com estes nomes na pasta `img/`:
`passo-1.png`, `passo-2.png` … `passo-7.png` (o que cada passo mostra está no modo "Passo a passo", etapa 3).
- **Apague ou cubra CPF, CNPJ, nome e telefone** antes de publicar.
- Prefira imagens leves (até ~150 KB cada). Enquanto o arquivo não existir, o espaço do print simplesmente não aparece; assim que você enviar com o nome certo, ele aparece sozinho.

## 5. Imprimir o cartaz

1. Abra `https://SEU-USUARIO.github.io/guia-contrata-mais-brasil/cartaz.html`
2. Confira o endereço embaixo do QR.
3. **Imprimir** → papel **A4**, margens **nenhuma**, marque **"Gráficos de plano de fundo"**.
4. Teste o QR com a câmera do celular antes de imprimir várias cópias.

Dá para gerar um cartaz com outro endereço ou instituição sem editar nada:
`cartaz.html?url=https://outro-endereco&inst=Nome da instituição&end=Rua, número - Bairro`
(o `&end=` é opcional e mostra o endereço embaixo do nome).

---

Créditos: QR code gerado com *QR Code Generator for JavaScript* © Kazuhiko Arase (licença MIT), embutido em `cartaz.html`.
