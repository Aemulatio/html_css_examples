# HTML Popover API: практическое объяснение

## Что это
Нативный способ показать всплывающий UI (подсказка, меню, панель действий) без тяжелого JS-кода.

## Ключевые режимы
- `popover` или `popover="auto"`: закрывается по `Esc`, клику вне, и при открытии другого auto-popover.
- `popover="manual"`: состояние закрытия/открытия полностью под твоим контролем.

## Базовый синтаксис
```html
<button popovertarget="tip">Показать</button>
<div id="tip" popover>Подсказка</div>
```

```html
<button popovertarget="menu" popovertargetaction="toggle">Меню</button>
<div id="menu" popover="manual">...</div>
```

## Доступные действия
`popovertargetaction`:
- `show`
- `hide`
- `toggle`

## Стилизация
Можно использовать псевдокласс `:popover-open`.

```css
[popover]:popover-open {
  animation: rise .14s ease;
}
```

## Когда использовать
- Короткие подсказки рядом с контролом.
- Небольшие контекстные меню.
- Быстрые action-панели.

## Когда не использовать
- Сложные диалоги с формами и фокус-ловушкой: для этого лучше `<dialog>`.
- Большие панели, которые должны вести себя как отдельный route/layout.

## Практические советы
1. Для простых подсказок выбирай `auto`.
2. Для кастомного поведения и внешнего state management выбирай `manual`.
3. Держи popover-контент компактным и контекстным.
4. Проверяй управление с клавиатуры (`Tab`, `Esc`).

## Что смотреть в демо
Файл: `pages/popover.html`
- Пример `auto` popover.
- Пример `manual` с `show/hide/toggle`.
- Стилизация через `:popover-open`.
