---
title: Element.setAttribute()
slug: Web/API/Element/setAttribute
translation_of: Web/API/Element/setAttribute
---
{{APIRef("DOM")}}Добавляет новый атрибут или изменяет значение существующего атрибута у выбранного элемента.

## Синтаксис

```
element.setAttribute(name, value);
```

- `name` - имя атрибута (строка).
- `value` - значение атрибута.

## Пример

В следующем примере, `setAttribute()` используется, чтобы установить атрибут {{htmlattrxref("disabled")}} кнопки {{htmlelement("button")}}, делая её отключённой.

```html
<button>Hello World</button>
```

```js
var b = document.querySelector("button");

b.setAttribute("disabled", "disabled");
```

{{ EmbedLiveSample('Пример', '300', '50', '', 'Web/API/Element/setAttribute') }}

## Примечания

При вызове на элементе внутри HTML документа, setAttribute переведёт имя атрибута в нижний регистр.

Если указанный атрибут уже существует, его значение изменится на новое. Если атрибута ранее не существовало, он будет создан.

Несмотря на то, что метод [`getAttribute()`](/ru/docs/DOM/element.getAttribute "DOM/element.getAttribute") возвращает null у удалённых атрибутов, вы должны использовать [removeAttribute()](/ru/docs/DOM/element.removeAttribute "DOM/element.removeAttribute") вместо _elt_.setAttribute(_attr_, null), чтобы удалить атрибут. Последний заставит значение `null` быть строкой `"null"`, которая, вероятно, не то, что вы хотите.

Использование setAttribute() для изменения определённых атрибутов особенно значимо в XUL, так как работает непоследовательно, а атрибут определяет значение по умолчанию. Для того, чтобы получить или изменить текущие значения, вы должны использовать свойства. Например, elt.value вместо elt.setAttribure('value', val).

Чтобы установить атрибут, которому значение не нужно, такой как, например, атрибут `autoplay` элемента {{HTMLElement("audio")}}, используйте null или пустое значение. Например: `elt.setAttribute('autoplay', '')`

{{DOMAttributeMethods}}

## Спецификация

- [DOM Level 2 Core: setAttribute](http://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-F68F082) (представлено в [DOM Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-setAttribute))
- [HTML5: APIs in HTML documents](http://www.whatwg.org/specs/web-apps/current-work/#apis-in-html-documents)
