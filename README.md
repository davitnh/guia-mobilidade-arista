# Guia de Mobilidade — Faria Lima 4509

Guia interativo com os locais próximos ao escritório da Arista.

## Estrutura

```
index.html          → página (layout, filtros, busca e botão "Checar rota")
data/locais.json    → todo o conteúdo do guia (edite aqui)
vercel.json         → configuração da Vercel
```

## Como editar o conteúdo

Tudo fica em `data/locais.json`. Para adicionar um local, copie um item de `locais` e ajuste:

```json
{ "nome": "Nome do local", "categoria": "restaurantes", "tipo": "Italiano",
  "endereco": "R. Exemplo, 123", "distancia": 400, "tempo": 6, "preco": "R$ 60" }
```

- `categoria` precisa ser um `id` existente em `categorias`.
- Campos opcionais: `preco`, `telefone`, `destaque`, `enderecoRota` (endereço usado só na rota do Google Maps).

## Rodar localmente

O site carrega o JSON via `fetch`, então precisa de um servidor (abrir o arquivo direto não funciona):

```bash
npx serve .
```

## Publicar

1. Suba esta pasta em um repositório no GitHub.
2. Na Vercel: **Add New → Project → Import** o repositório.
3. Framework Preset: **Other** · sem build command · Output: raiz. Clique em **Deploy**.
