Пояснения к файлу grid.html
боюсь, что намудрила и все можно было сделать сильно проще. Плюс не разобралась как в итоге выровнять текст, чтобы он был по центру в каждом элементе (еще1, еще2, еще3)
А в футере кажется намудрила с размерами и расположением элементов в нем (секция 1,2,3,4)

Пояснения к файлу figmagrid.html
Я выбрала такой макет, который, как мне показалось нет смысла полностью делать на гриде (по крайней мере у меня не вышло, так как текст в хедере и сайдбаре не получилось расположить как нужно, поэтому использовала flex. Не знаю можно ли так было сочетать flex и grid)

Вопросы. Неделя 6
1. Что за единица измерения - fr?
С ее помощью задается ширина треков. Рассчитывается исходя из доступного пространства в grid-контейнере.

2. Как можно задать грид с 5 колонками шириной по 20%? Минимум 2 способа.
grid-template-columns: 20% 20% 20% 20%  20%
grid-template-columns: repeat (5, 20%)
grid-template-columns: 1fr 1fr 1fr 1fr 1fr
grid-template-columns: repeat (5, 1fr)

3. Самостоятельно разберитесь, что такое auto-fill и auto-fit ?
Они используются внутри функции repeat вместо цифр

4. Как сделать такую табличку? Параметры: первая колонка шириной 100 пикселей, вторая 30%. Первая строчка высотой 200 пикселей, вторая строчка 100 пикселей.

5. Как сделать такое выравнивание в грид-контейнере? 
Justify-content: space-between

6. Что такое и как задается grid area?
Это область, в которой могут находиться несколько grid элементов. 
Сокращенная запись четырех свойств: grid-row-start, grid-column-start, grid-row-end, grid-column-end
Определяет размер и положение элементов сетки

7. C помощью grid area помимо цифровых значений можно задать имена ячейкам и далее с помощью свойства grid-templates-areas мы располагаем эти ячейки в нашей сетке.                                                                                                                                       

пример
.item-1 {
  grid-area: header;
}
.item-2 {
  grid-area: main;
}
.item-3 {
  grid-area: sidebar;
}
.item-4 {
  grid-area: footer;
}

.container {
  grid-template-columns: 50px 50px 50px 50px;
  grid-template-rows: auto;
  grid-template-areas:
    'header header header header'
    'main main . sidebar'
    'footer footer footer footer';
}
значит сверху будет header на всю длину, ниже строка делится на 4 части, 2 из них будет занимать main, одна часть будет пустой (тк помечена точкой) и следом будет sidebar. А снизу будет располагаться footer на всю длину как и header. В зависимости от того, как мы расположим названия ячеек, будут располагаться сами ячейки

8. Каким свойством можно задать такое поведение элементов?
с помощью ключевого слова auto-fit. При расширении страницы сам макет также будет растягиваться, ставя на освободившееся место те ячейки, которые были на следующей строке.

9. Самостоятельно разберитесь, как работают именованные линии? Есть ли какие-то рекомендованные правила наименований? Если да, то какие?
Чтобы разместить элементы в сетке мы указываем номера линий, на которых они должны располагаться, Но вместо цифр мы можем задавать им имена. Это упрощает отображение сайта, если он переведен на язык, который пишется справа налево.
Имена линиям задаются в квадратных скобках [ … ], а между для именами указывается ширина столбца или высота строки, которые находятся между этими линиями,имя может быть любым, кроме ключевого слова span.
Как правило, к именам линий добавляют суффиксы -start и -end (например main-start, main-end)
Часто одна линия заканчивается там, где начинается другая тогда мы просто прописываем имена через пробел в квадратных скобках [main-start sidebar-start]
Мы можем использовать имена линий и номера одновременно.

10. Как проще всего задать 12 одинаковых по ширине колонок?
grid-template-columns: repeat (12, 1fr);

ПРАКТИЧЕСКОЕ ЗАДАНИЕ:
1. Пройти игру

<img width="1226" alt="gridgarden" src="https://user-images.githubusercontent.com/110172816/188288448-cee7c3c4-1819-4312-943a-674300fed29e.png">



