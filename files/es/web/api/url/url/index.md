---
title: URL()
slug: Web/API/URL/URL
translation_of: Web/API/URL/URL
---

{{APIRef("URL API")}}

El constructor **`URL()`** devuelve un objeto {{domxref("URL")}} recién creado que representa la URL definida por los parámetros.

Si la URL base dada o la URL resultante no son URL válidas, se lanza un {{domxref("DOMException")}} de tipo `SYNTAX_ERROR`.

{{AvailableInWorkers}}

## Sintaxis

```
url = new URL(url, [base])
```

### Parámetros

- `url`
  - : Un {{domxref("USVString")}} que representa una URL absoluta o relativa. Si _url_ es una URL relativa, se requiere _base_, y se usará como URL base. Si url es una URL absoluta, se ignorará una _base_ determinada.
- `base` {optional_inline}}
  - : Un {{domxref("USVString")}} representa la URL base a usar en caso de que la URL sea una URL relativa. Si no se especifica, el valor predeterminado es `''`.

> **Nota:** Aún puede usar un objeto {{domxref("URL")}} existente para la base, que se enchufa al atributo {{domxref("DOMString.href","href")}} del objeto.

### Excepciones

| Excepción   | Explicación                                                                                              |
| ----------- | -------------------------------------------------------------------------------------------------------- |
| `TypeError` | _url_ (en el caso de URL absolutas) o _base_ + _url_ (en el caso de URL relativas) no es una URL válida. |

## Ejemplos

```js
// Urls base
var m = 'https://developer.mozilla.org';
var a = new URL("/", m);                                // => 'https://developer.mozilla.org/'
var b = new URL(m);                                     // => 'https://developer.mozilla.org/'

        new URL('en-US/docs', b);                      // => 'https://developer.mozilla.org/en-US/docs'
var d = new URL('/en-US/docs', b);                     // => 'https://developer.mozilla.org/en-US/docs'
        new URL('/en-US/docs', d);                     // => 'https://developer.mozilla.org/en-US/docs'
        new URL('/en-US/docs', a);                     // => 'https://developer.mozilla.org/en-US/docs'

        new URL('/en-US/docs', "https://developer.mozilla.org/fr-FR/toto");
                                                       // => 'https://developer.mozilla.org/en-US/docs'

        new URL('/en-US/docs', '');                    // Provoca una excepción TypeError ya que '' no es una URL válida
        new URL('/en-US/docs');                        // Provoca una excepción TypeError ya que '/en-US/docs' no es una URL válida
        new URL('http://www.example.com', );           // => 'http://www.example.com/'
        new URL('http://www.example.com', b);          // => 'http://www.example.com/'

        new URL("//foo.com", "https://example.com")    // => 'https://foo.com' (ver URL relativas)
```

## Especificación

| Especificación                                                   | Estado               | Comentario          |
| ---------------------------------------------------------------- | -------------------- | ------------------- |
| {{SpecName('URL', '#constructors', 'URL.URL()')}} | {{Spec2('URL')}} | Initial definition. |

## Compatibilidad del navegador

{{Compat("api.URL.URL")}}

## Ver también

- La interfaz a la que pertenece: {{domxref("URL")}}.
