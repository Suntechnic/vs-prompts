---
agent: 'agent'
description: 'Переформатирование шаблона компонента Bitrix в соотвествии с моими соглашениями.'
name: 'bx-trf'
---

Пространство имен: ${input:namespace:bitrix}
Имя компонента: ${input:componentName}
Имя шаблона: ${input:templateName:'.default'}

Найди дефолтный шаблон компонента по пути:
`local/templates/.default/components/${namespace}/${componentName}/${templateName}/`

Переформатируй все *.php файлы в соответствии с соглашениями проекта:
- Переименуй переменные согласно префиксам ($lst*, $dct*, $ref* и т.д.)
- Замени var_dump() на \Kint::dump()
- Оформи блоки if/foreach с HTML через альтернативный синтаксис (: / end*)
- Добавь PHPDoc блоки к функциям если их нет
- Комментарии на русском языке
- Удали все табличные теги (`<table>`, `<tr>`, `<td>`, `<th>`, `<thead>`, `<tbody>`, `<tfoot>`) и замени их на div-структуру с CSS классами для стилизации