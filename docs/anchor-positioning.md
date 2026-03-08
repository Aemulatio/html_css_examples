# CSS Anchor Positioning: краткий гайд

## Что это
`Anchor Positioning` позволяет размещать один элемент относительно другого (anchor) без ручного JS-пересчета координат.

## Базовая идея
1. У якоря задаешь имя: `anchor-name: --id;`
2. Плавающему элементу задаешь: `position-anchor: --id;`
3. Координаты берешь через `anchor(...)`.

```css
.trigger { anchor-name: --t; }

.pop {
  position: absolute;
  position-anchor: --t;
  left: anchor(left);
  top: calc(anchor(bottom) + 8px);
}
```

## Когда полезно
- подсказки и popover-панели;
- badge/label рядом с динамическим контентом;
- маленькие контекстные меню.

## Ограничения
- Фича экспериментальная, поддержка браузеров неполная.
- В проде нужна progressive enhancement стратегия (fallback на обычный absolute/fixed или JS).

## Практический fallback
- База: простой layout без anchor.
- Улучшение: `@supports` с anchor-функциями.

```css
.pop { position: absolute; left: 0; top: 100%; }

@supports (left: anchor(left)) {
  .pop {
    left: anchor(left);
    top: calc(anchor(bottom) + 8px);
  }
}
```

## Что смотреть в демо
Файл: `pages/anchor-positioning/index.html`
- подсказка, привязанная к кнопке;
- badge, привязанный к чипу;
- минимальный шаблон для копирования.

