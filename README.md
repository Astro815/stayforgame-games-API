# stayforgame-games-API
Conecte os jogos da stayforgame no seu site!

## Como carregar a API
1. Abra seu site onde insira as informações dos jogos e crie um arquivo chamado ```load_api_sfg.js```
2. Passe esse codigo para dentro do arquivo
```js
var jsonAPI = "";

loadApiSfg("https://raw.githubusercontent.com/Astro815/stayforgame-games-API/main/game-api.json", function(data) {
    jsonAPI = JSON.parse(data);
    // use a variavel "jsonAPI" ou "data" para coletar as informações
    // usando "document.querySelector" para alterar as informações do site.
});

function loadApiSfg(file, callback) {
    var rawFile = new XMLHttpRequest();
    rawFile.overrideMimeType("application/json");
    rawFile.open("GET", file, true);
    rawFile.onreadystatechange = function() {
        if (rawFile.readyState === 4 && rawFile.status == "200") {
            callback(rawFile.responseText);
        }
    }
    rawFile.send(null);
}
```
3. Após isso crie o codigo para inserir as informações no site
4. Linke o arquivo com a pagina usando:
```html
<script src="./load_api_sfg.js"></script>
```
5. E Finalizado! você já tem as informações dos jogos!
## Incluso
- Nome ```name```
- Versão ```version```
- Descrição ```dec```
- Como Jogar ```cmplay```
- Imagem ```img```
- Capa de Fundo ```cap```
- Link da Itch.Io ```itchio```
- Link da Game Jolt ```gamejolt```
- Novidades ```new```
- - Adições ```added```
- - Modificações ```modified```
- - Remoções ```remove```
- - Remoções de Bugs ```remove_bug```
- Creditos ```credit```

## Caminhos para os valores
#### Nome
```js
jsonAPI.games.nomeDoGame.name
```
#### Versão
```js
jsonAPI.games.nomeDoGame.version
```
etc...
