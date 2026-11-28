# Ana Lu Vibes: como cuidar do seu site pelo Claude

Oi, Lua! Esse é o seu site novo, na identidade da Analu Vibes: branco, dourado e prata, com a fonte Cinzel, a sua logo original e o texto "Quem somos" do Instagram. Cada peça tem um botão **Comprar** que já abre o seu WhatsApp (21 97680-4548) com o nome e o preço da peça escritos.

Você não precisa saber nada de código. Quem mexe no site é o seu Claude, e você só pede.

---

## Passo 1: colocar o site na sua conta (só uma vez)

1. Baixe o arquivo **analuvibes-site.zip** que o Fernando te mandou e descompacte. Vai aparecer a pasta `analuvibes-site`, com o `index.html` e a pasta `img` cheia de fotos.
2. Abra o **Claude Code** (no app do Claude, na aba Code, ou em claude.ai/code) e abra essa pasta.
3. Cole esta mensagem:

> Esta pasta é o site da minha marca, a Ana Lu Vibes. Publique como um artifact com o título "Ana Lu Vibes", enviando o index.html e todas as fotos da pasta img. Depois me mande o link.

4. Pronto, o site agora é seu. Guarde o link.

## Passo 2: deixar o site aberto pros clientes

1. Abra o link do site.
2. Toque em **Compartilhar** e escolha a opção de link público, que qualquer pessoa pode abrir.
3. Copie o link e coloque na bio do Instagram (@_analuvibes), no status e no WhatsApp Business.

---

## Como postar peça nova, trocar foto ou mudar preço

Sempre no Claude Code, com a pasta `analuvibes-site` aberta. Mande as fotos junto com a mensagem e peça do jeito que você fala. Exemplos prontos:

**Peça nova**
> Adiciona no site a peça nova "Conjunto Sol Rosa", coleção Tropical, R$ 259,90. Cores: rosa e lilás. Descrição: "Top cruzado e short de cós alto, pra treinar e ir pra praia." Marca como novidade. A foto está em anexo. Depois publica a nova versão no meu artifact Ana Lu Vibes.

**Trocar foto**
> Troca a foto do Macacão Aura Black por esta nova e publica.

**Mudar preço**
> Muda o preço de todos os Flare Boss para R$ 299,90 e publica.

**Peça esgotada**
> Tira o Macaquinho Energy Off do site e publica.

**Coleção nova**
> Cria a coleção "Verão 27" e coloca nela estas 3 peças (fotos em anexo, preço R$ 239,90 cada). Publica.

**Mudar o WhatsApp**
> Troca o número do WhatsApp do site para 55 21 9XXXX-XXXX e publica.

Depois de cada pedido, abra o link e confira. Se algo não ficou do seu jeito, é só falar, por exemplo: "deixa a foto mais pra cima" ou "a descrição ficou grande, encurta".

---

## Dicas para as fotos ficarem lindas

- Use foto em pé, na **vertical**. O site mostra as fotos no formato de retrato (4:5).
- Fundo claro, luz do dia, a peça inteira aparecendo.
- Cada cor vira um card com o próprio botão de compra. Mande de 4 a 6 fotos por cor (frente, costas, lado e um detalhe): elas rolam pro lado no site.
- Dê nomes simples pros arquivos, sem acento: `sol-rosa.jpg`, `aura-verde.jpg`.

## Para o Claude (se ele perguntar onde mexer)

Todas as peças ficam no `index.html`, dentro do bloco marcado **EDITE AQUI**, no fim do arquivo:

- `WHATSAPP`: o número que recebe os pedidos.
- `COLECOES`: o nome de cada coleção (vira um botão de filtro).
- `PRODUTOS`: uma linha por peça, com `nome`, `colecao`, `preco`, `fotos` (lista; a 1ª é a capa e, com 2 ou mais, as fotos rolam pro lado no card e na ficha), `cores`, `desc` (frase curta do card), `sobre` (texto completo da peça, igual ao do catálogo do WhatsApp; `\n\n` separa parágrafos), `det` e `novo: true` para o selo de Novidade.
- Tocar na foto ou em "Sobre a peça" abre a ficha da peça, com fotos grandes, o texto `sobre` e os detalhes.

As fotos ficam na pasta `img/`, e a logo está em `img/logo.png`, `img/logo-sol.png` e `img/logo-nome.png`. Mantenha o visual em branco, dourado e prata, com a fonte Cinzel. Depois de editar, ele publica a nova versão no mesmo artifact. Assim o link continua igual e quem já tem o link vê o site atualizado.
