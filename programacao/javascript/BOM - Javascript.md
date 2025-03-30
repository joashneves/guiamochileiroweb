Se o DOM (Document Object Model) mexe diretamente com o HTML da pagina, o BOM (Browser Object Model) mexe diretamente com o Browser(o navegador), muitas vezes é referido como métodos e propriedades da lista técnica.

## Objeto windows
Todos os objetos, funções e variáveis JavaScript globais tornam-se automaticamente membros do objeto window.
```javascript
window.document.getElementById("header");
// É o mesmo que 
document.getElementById("header");
```
## Janelas
Comandos

```javascript
let w = window.innerWidth;  // a altura interna da janela do navegador (em pixels) 
let h = window.innerHeight; // a largura interna da janela do navegador (em pixels)

// Outros metodos 
window.open() // abrir uma nova janela
window.close() // fechar a janela atual
window.moveTo() // mover a janela atual
window.resizeTo() // redimensionar a janela atual
```

