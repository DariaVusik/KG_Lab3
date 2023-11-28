# Лабораторная работа 3 Базовые растровые алгоритмы
## Цель работы
Изучить работу базовых растровых алгоритмов: пошаговый алгоритм, алгоритм Брезенхема;
## Задачи работы
1. Создать приложение/веб-приложение, позволяющее иллюстрировать работу алгоритмов
2. Реализовать дружелюбный и удобный интерфейс, возможность задавать масштаб; обязателен вывод системы координат, осей, линий сетки, подписей;
## Использованные средства разработки
Язык программирования Java
## Описание алгоритмов
### Пошаговый алгоритм
Принцип работы пошагового растрового алгоритма для построения отрезков:
1. Задаются координаты начальной точки (x0, y0) и конечной точки (x1, y1) отрезка.
2. Вычисляются разности между координатами конечной и начальной точек: dx = x1 - x0 и dy = y1 - y0.
3. Определяется основное направление растрового сканирования, которое зависит от знаков dx и dy.
Например, если dx >= 0 и |dx| >= |dy|, то выбирается горизонтальное направление (слева направо). В противном случае выбирается вертикальное направление.
4. Вычисляется значение наклона (slope) отрезка, которое равно dy/dx.
5. Инициализируется текущая точка (x, y) равной начальной точке (x0, y0).
6. Закрашивается текущий пиксель, соответствующий текущей точке (x, y).
7. Если текущая точка достигла конечной точки (x1, y1), алгоритм завершается. В противном случае переходим к следующему шагу.
8. В зависимости от основного направления растрового сканирования, вычисляется следующий пиксель для проверки. Например, если выбрано горизонтальное направление, то следующий пиксель будет (x + 1, y). Если выбрано вертикальное направление, то следующий пиксель будет (x, y + 1).
9. Используется значение наклона (slope) для определения, следует ли переместиться в горизонтальном или вертикальном направлении. Если |slope| <= 1, то изменяем координату x на единицу, иначе изменяем координату y на единицу.
10. Повторяем шаги 6-9 для каждого пикселя, пока не достигнута конечная точка.

Пошаговый растровый алгоритм для построения отрезков является более простым и менее точным по сравнению с алгоритмом Брезенхэма. 
Он может привести к некоторым артефактам, таким как зазубренные края и неровные линии. 
Тем не менее, этот алгоритм все еще используется в некоторых простых приложениях или случаях, где точность не является первоочередным требованием
### Алгоритм Брезенхема
Принцип работы алгоритма:
1. Задаются координаты начальной точки (x0, y0) и конечной точки (x1, y1) отрезка.
2. Вычисляются разности между координатами конечной и начальной точек: dx = x1 - x0 и dy = y1 - y0.
3. Определяется основное направление растрового сканирования, которое зависит от знаков dx и dy. Например, если dx >= 0 и |dx| >= |dy|, то выбирается горизонтальное направление (слева направо). В противном случае выбирается вертикальное направление.
4. Вычисляется параметр ошибки (error) и инициализируется с нулевым значением. Этот параметр используется для аппроксимации отрезка и определения следующего пикселя на каждом шаге.
5. Задается текущая точка (x, y) равная начальной точке (x0, y0).
6. Закрашивается текущий пиксель, соответствующий текущей точке (x, y).
7. Если текущая точка достигла конечной точки (x1, y1), алгоритм завершается. В противном случае переходим к следующему шагу.
8. В зависимости от основного направления растрового сканирования, вычисляется следующий пиксель для проверки. Например, если выбрано горизонтальное направление, то следующий пиксель будет (x + 1, y). Если выбрано вертикальное направление, то следующий пиксель будет (x, y + 1).
9. Обновляется значение параметра ошибки на основе разности между dx и dy и текущим значением ошибки.
10. Если значение параметра ошибки становится больше или равно половине основного шага (пикселя), то корректируются координаты текущей точки в соответствии с основным направлением сканирования.
Если выбрано горизонтальное направление, то если error >= dx/2, увеличиваем y на единицу и обновляем значение ошибки error -= dx.
Если выбрано вертикальное направление, то если error >= dy/2, увеличиваем x на единицу и обновляем значение ошибки error -= dy.
11.Повторяем шаги 6-10 для каждого пикселя, пока не достигнута конечная точка.

Алгоритм Брезенхэма позволяет эффективно и точно аппроксимировать отрезки на растровых экранах.
Он минимизирует ошибки округления и обеспечивает плавные линии.Благодаря своей эффективности и точности,
алгоритм Брезенхэма широко используется в графических приложениях и компьютерной графике для рисования отрезков и линий.
## Ход работы
1. Создание главного класса RasterAlgorithmsApp, служащего главным окном
2. Создание класса DrawingPanel, который показывает график
3. Реализация алгоритмов 
4. Добавление возможности масштабирования и перемещения графика
5. Создание пользовательского интерфейса
## Вывод:
В ходе выполнения данной работы я:
1. создала приложение, иллюстрировать работу базовых растровых алгоритмов: пошаговый алгоритм и алгоритм Брезенхема
2. закрепила полученные лекционные знания про пошаговый алгоритм и алгоритм Брезенхема
3. получила дополнительный опыт по проектированию приложений
4. углубила знания языка Java
5. получила дополнительный опыт работы с системой контроля версий Git
