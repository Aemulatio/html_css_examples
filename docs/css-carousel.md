# CSS Carousel (MDN Overflow): практическое объяснение

## Что это
Карусель на основе overflow + scroll snap с нативными CSS pseudo-elements карусели.

## Ключевые части
- `scroll-snap-type: x mandatory` для прилипания слайдов;
- `::scroll-button(left/right)` для кнопок вперед/назад;
- `::scroll-marker-group` и `::scroll-marker` для пагинации;
- `:target-current` для активного маркера.

## Базовый скелет
```css
.carousel {
  overflow-x: scroll;
  scroll-snap-type: x mandatory;
  scroll-marker-group: after;
}

.carousel > li {
  flex: 0 0 100%;
  scroll-snap-align: center;
}
```

## Практические советы
1. Делай graceful fallback: без pseudo-elements должен оставаться рабочий горизонтальный скролл.
2. Используй заметные контрасты для стрелок/маркеров.
3. Проверяй поддержку фич в целевых браузерах.

## Что смотреть в демо
Файл: `pages/css-carousel/index.html`
- реализация карусели в стиле MDN Overflow Guide;
- стилизованные стрелки и маркеры.

