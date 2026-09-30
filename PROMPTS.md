# Промпты для Higgsfield - осенняя коробка OZONEBOX

Генерируете вы в вебе Higgsfield, я проверяю и собираю. Готовые файлы кладите в `mockups/v2-premium-osen/assets/src/` под именами из таблиц (формат PNG, без пересжатия).

Общие правила для всех кадров:
- Модель для картинок: **Nano Banana Pro** (лучше всех держит референсы). Если лица флаконов плывут, пробуем GPT Image 2 с теми же референсами.
- Формат **16:9**, разрешение **2K**. Делайте 2-4 варианта и присылайте лучший, или все, если не уверены.
- Промпты на английском: модели так точнее. Стилевой блок (STYLE) вставляется в каждый кадр **одинаково, слово в слово**: на нём держится единый мир.
- На картинке не должно быть никакого текста. Все надписи я ставлю поверх HTML-ом.

## STYLE - вставлять в каждый промпт без изменений

```
Ultra-photorealistic premium cosmetics still life, autumn forest floor at golden hour. Deep dark moss, scattered fallen maple and oak leaves in ochre, copper and rust, a few wet dark stones, tiny dew drops on everything. One low warm sunbeam falls through the trees as a soft oval pool of light in the centre of the frame, everything outside it sinks into deep near-black shadow at the edges and corners, like light through a window. Subtle warm rim light from behind the hero object outlines its silhouette, faint dust motes glowing in the beam, light morning mist far in the background. Colour palette: near-black forest #0E120E, moss #2F3A24, ochre #B8742A, copper #8A4B22, muted gold #C9A55B. Shot on medium format, 85mm, shallow depth of field, editorial luxury skincare campaign, matte film grain. Absolutely no text, no letters, no numbers, no logos anywhere except where described.
```

## Пакет 1 - первый экран

### S0 - закрытая коробка в сцене (`s0.png`)

Референсы (загрузить как image references): `Рефы/Основной реф.jpg` (композиция и пятно света), `Рефы/контровой свет.jpg` (контровой свет), `Рефы/коробка.png` (форма коробки), `Рефы/логотип.png` (знак).

```
[STYLE]
Hero object: a single premium gift box resting on the moss exactly in the centre of the light pool, seen from a slightly high three-quarter angle, like the bottle in the first reference. The box is a rigid square-ish cube with a separate lid, same proportions as the white box reference, but redesigned as luxury packaging: soft-touch matte black paper, crisp sharp edges, a thin gloss-black debossed emblem on the lid in the shape of a rounded square outline with a small drop at its lower right corner (the mark from the logo reference, no lettering). A wide satin ribbon in muted brushed gold #C9A55B wraps the box crosswise and is tied on top in a flat, neat bow; the ribbon ends lie on the moss. Where the ribbon crosses at the front sits one small round enamel seal in cobalt blue #3C6DF0 shaped like a droplet - the only cool colour in the image. A few maple leaves have fallen onto the lid, dew drops on the black surface catch the sun. Leave calm empty dark space in the lower left third of the frame for a headline.
```

Проверка перед отправкой: коробка по центру, лента золотая и не жёлтая, синяя капля есть и она единственная холодная точка, в левом нижнем углу тёмное пустое место под текст, букв нигде нет.

### S0-open - та же сцена, коробка открыта (`s0-open.png`)

Режим **редактирования** (edit / image-to-image) выбранного `s0.png`. Референсы: `s0.png` + пакшоты `Рефы/1.png`, `2.png`, `3.png`, `4.png`.

```
Keep this exact image identical - same camera, same light, same moss, leaves, box position and shadows. Change only the box: the gold ribbon is untied and lies loosely on the moss, the lid is lifted off and leans against the right side of the box. Inside the open black box, on a dark copper satin lining, stand four skincare products upright side by side, from left to right: a white rounded jar with a white ribbed screw cap (reference 2), a tall white airless pump bottle with a clear cap (reference 3), a tall white flip-cap shampoo bottle (reference 1), a tall white airless pump bottle with a clear cap (reference 4). Copy the shape, cap and label colours of each product from its reference as closely as possible. Dew drops on the bottles, warm rim light outlining each one. No new text.
```

Проверка: всё, кроме коробки, совпадает с `s0.png` (я буду накладывать одно на другое, любая сдвинутая тень заметна). Флаконы похожи на настоящие по форме и цвету. Если надписи на этикетках кривые, это нормально: настоящие этикетки наложу я.

### Вырезки (`s0-box-cut.png`, `s0-open-cut.png`)

В Higgsfield инструментом удаления фона (Remove Background) по `s0.png` и `s0-open.png`: оставить только коробку (вместе с лентой) и открытую коробку с флаконами, фон прозрачный. Нужно, чтобы заголовок проходил **под** коробкой: фон ниже, текст в середине, вырезанная коробка сверху. Если удаление фона съест ленту на мху, пришлите как есть: края я поправлю.

### Статус пакета 1 (30.09.2026)

`s0.png` и `s0-open.png` утверждены и лежат в `assets/src/`. Осталось два действия в Higgsfield:
1. **Upscale ×2** обоих кадров (меню справа → Upscale). Сейчас 1376×768, первый экран на весь монитор будет мыльным. Скачать как `s0@2x.png` и `s0-open@2x.png`.
2. **Remove background** по увеличенному `s0@2x.png` → `s0-box-cut.png` (только коробка с лентой).

## Пакет 2 - крупные планы флаконов

Камера подходит к каждому флакону всё ближе. Порядок идёт слева направо, как флаконы стоят в коробке, поэтому камера ведёт вдоль них одним движением:

| Кадр | Флакон | Пакшот-референс |
|---|---|---|
| `p1.png` | «ОТРИ 6000», белая банка с ребристой крышкой | `Рефы/2.png` |
| `p2.png` | Ozodermis крем для ног 12,5%, флакон с помпой | `Рефы/4.png` |
| `p3.png` | Ozodermis шампунь 2%, флип-крышка | `Рефы/1.png` |
| `p4.png` | Ozone Cream эмульсия для лица, флакон с помпой | `Рефы/3.png` |

Как делать каждый: откройте `s0-open.png` в Higgsfield → поле «Describe how to edit image...» → «+» → прикрепите пакшот из таблицы → вставьте промпт, подставив название флакона. После генерации **Upscale ×2**.

```
Same scene, same golden-hour sunbeam, same moss, leaves, copper satin lining and black box. Move the camera much closer: a tight, eye-level macro close-up of the [PRODUCT: e.g. white round jar with a white ribbed screw cap] standing in the open box. The product fills about two thirds of the frame height, centred, label facing the camera, perfectly sharp. The other bottles next to it are soft out-of-focus shapes, the moss and fallen maple leaves in the background melt into warm bokeh in ochre, rust, red and yellow. Warm rim light outlines the silhouette of the product, tiny dew drops on its surface catch the light, faint dust motes in the beam. The label must match the attached product photo exactly: same layout, colours, logo and lettering; do not invent new text. Deep dark shadow at the frame edges. Photorealistic, medium format, 100mm macro, shallow depth of field, matte film grain.
```

Проверка: надписи на этикетке читаются и совпадают с пакшотом. Если хоть одна буква кривая, всё равно присылайте: это как раз тот кадр, где я наложу настоящую этикетку, а видео потом упрётся в исправленную картинку.

## Обновление 30.09.2026 - кадры перегенерированы в 4K (GPT Image 2.5)

Пакеты 1-2 выше устарели: все кадры переделаны через коннектор Higgsfield на GPT Image 2.5 в 4K, этикетки перенесены с пакшотов. Готовые кадры для видео лежат в `mockups/v2-premium-osen/for-video/`:
`s0.png` (закрытая коробка), `s0-open.png` (открытая), `p1.png`-`p4.png` (крупные планы), `leg0-last.png` (последний кадр готового L0).

**L0 уже сделан** (`assets/vid/leg0.mp4`, Seedance 2.0 1080p, bitrate high). Следующий - L1 со стартом `leg0-last.png`.

## Пакет 3 - видео

Модель в Higgsfield: **Seedance 2.0**, **1080p**, mode **std**, bitrate **high**, формат **16:9**, длительность **8 с**, звук выключен. Если Higgsfield предложит пресет («IN THE DARK» и т. п.) - откажитесь: пресет не держит стартовый и конечный кадр. В каждом отрезке загружаются **Start frame** и **End frame** из таблицы.

**Порядок строго по одному.** Прислали видео отрезка → я вырезаю его настоящий последний кадр (`leg0-last.png` и так далее) → он и есть Start frame следующего. Без этого на стыках будет прыжок.

| Отрезок | Start frame | End frame | Движение |
|---|---|---|---|
| L0 | `s0.png` | `s0-open.png` | лента развязывается, крышка поднимается |
| L1 | `leg0-last.png` (от меня) | `p1.png` | наезд в коробку к банке «ОТРИ» |
| L2 | `leg1-last.png` | `p2.png` | вправо вдоль флаконов к крему для ног |
| L3 | `leg2-last.png` | `p3.png` | дальше вправо к шампуню |
| L4 | `leg3-last.png` | `p4.png` | дальше вправо к эмульсии |
| L5 | `leg4-last.png` | `s0-open.png` | камера поднимается и открывает всю коробку, финал |

Хвост стиля (TAIL) для всех видео:
```
Photorealistic autumn forest floor, golden-hour sunbeam, deep near-black shadows at the edges, warm rim light, dew drops, fallen maple leaves, matte film grain. Smooth, graceful, slow motion, subtle parallax. No text, no captions.
```

**L0**
```
Single continuous cinematic camera move, no cuts. The camera slowly glides forward toward the black gift box on the moss. The gold satin ribbon unties itself and slides down onto the moss, the lid lifts off and settles leaning against the right side of the box, revealing four white skincare bottles standing on copper satin inside. In the final second, settle into a slow, steady forward glide toward the open box. [TAIL]
```

**L1**
```
Single continuous cinematic camera move, no cuts. Continue the same slow, steady forward glide. The camera pushes in over the edge of the open box and down toward the white round jar on the left, until it nearly fills the frame, the other bottles drifting out of focus. In the final second, settle into a slow, steady glide, holding on the jar label. [TAIL]
```

**L2, L3, L4** (одинаковые, меняется только флакон)
```
Single continuous cinematic camera move, no cuts. Continue the same slow, steady glide. The camera tracks low and level to the right along the row of bottles inside the box, the bottles sliding past in soft foreground parallax, and comes to rest in a close-up of the [NEXT PRODUCT]. In the final second, settle into a slow, steady glide, holding on its label. [TAIL]
```

**L5** (финал: камера здесь может отъехать, после него стыков нет)
```
Single continuous cinematic camera move, no cuts. Continue the same slow, steady glide, then rise smoothly and pull back as the full open black box with all four bottles on copper satin reveals below, the untied gold ribbon and autumn leaves on the moss around it. [TAIL]
```

Если Higgsfield отклонит отрезок по фильтру контента, просто перезапустите: у Seedance это случается без причины и проходит со второй-третьей попытки.
