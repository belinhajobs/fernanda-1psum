# Melchionna Ipsum API
API perfeita para popular seu projeto com frases de uma deputada brasileira com um vocabulário um tanto peculiar e cheio de personalidade.

## Rotas
A API só trabalha com métodos GET porque é só isso que precisamos mesmo.

### `/`
Retorna todas as frases guardadas do Melchionna Ipsum.

### `/paragrafos/{n}`
Retorna um parágrafo. Caso precise de mais de um parágrafo, especifiquis ele após a barra.

Por exemplo, `https://[LINK]/paragrafos/5` vai retornar cinco parágrafos de Mussum Ipsum.

### `/frases/{n}`
Retorna `"Política não é para os engravatados!"`. Para retornar uma outra frase, diga seu index depois da barra.

Por exemplo, `https://fernanda-1psum.vercel.app/frases/1` retorna `"senhores vereadores, senhoras vereadoras,"`. Cuidado para não estourar o array.

### `/frases/random`
Retorna uma frase aleatória da Fernanda Melchionna

## Troubleshooting

### Parâmetro fora do limite
Na rota `/frases/{n}`, caso seja dado um número que não esteja dentro do index das frases, a API vai retornar um objeto de `err`.

#### Exemplo
url: `https://fernanda-1psum.vercel.app/frases/19`
```json
{
    "err": {
        "causa": "Parâmetro fora do limite",
        "limite": {limite do array}
    }
}
```
O array de palavras contém 20 palavras até hoje (24/12/2024).
### Parâmetro NaN
Nas rotas `/paragrafos/{n}` e `/frases/{n}`, caso {n} não seja numérico, a API vai retornar um objeto `err`.

#### Exemplo
url: `https://mipsum.herokuapp.com/paragrafos/n=12`
```json
{
    "err": {
        "causa": "Parâmetro NaN",
        "parametro": "n=12"
    }
}
```

## Deploy
Para o deploy é necessário o git, nodejs e npm instalados.
+ baixe o projeto com `git clone` ou download convencional;
+ instale as dependências do node com o `npm i`;
+ inicie o servidor com `npm start`.

# Reconhecimentos
Essa API é uma síntese inspirada no Mussum Ipsum do [mussum-ipsum](https://github.com/diegofelipece/mussum-ipsum) do Diego Felipe. 