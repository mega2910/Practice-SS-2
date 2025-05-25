?вам даётся 2 пути до дома от точки А - колледж, до точки D - дом. AB - пешком, BC - на автобусе, но нужно ещё подождать 10 минут, CD - пешком или весь путь AD - пешком. вывести всю промежуточную информацию.

start
? Объявление переменных с расстояниями (км)
new AB number
set AB 2               ? Расстояние А-В пешком
new BC number
set BC 5 			   ? Расстояние B-C на автобусе
new CD number
set CD 1               ? Расстояние C-D пешком
new AD number
set AD 0	   		   ? Весь путь A-D пешком
set AD AB
set AD AD + BC
set AD AD + CD

? Задаю скорость
new walk_speed number
set walk_speed 5    ? Скорость пешком (км/ч)
new bus_speed number
set bus_speed 30    ? Скорость автобуса (км/ч)
new bus_wait number
set bus_wait 10     ? Ожидание автобуса (мин)

? Расчет времени для маршрута1 (AB-BC-CD)
new time_ab number
set time_ab (AB / walk_speed) * 60    ? Время А-В в минутах
new time_bus number
set time_bus (BC / bus_speed) * 60    ? Время в автобусе без ожидания
new time_bc_total number
set time_bc_total time_bus + bus_wait ? Общее время B-C с ожиданием
new time_cd number
set time_cd (CD / walk_speed) * 60    ? Время C-D
new total_route1 number
set total_route1 time_ab + time_bc_total + time_cd

? Расчет времени для маршрута2 (AD)
new time_ad number
set time_ad (AD / walk_speed) * 60
new total_route2 number
set total_route2 time_ad

? Вывод данных о маршрутач 
log string "--- Маршрут1 (AB-BC-CD) ---"
log string "А-В: " >> AB >> " км / " >> time_ab >> " мин"
log string "B-C: " >> BC >> " км / " >> time_bus >> " мин + " >> bus_wait >> " мин ожидания"
log string "C-D: " >> CD >> " км / " >> time_cd >> " мин"
log string "Итого: " >> total_route1 >> " мин"

log string "--- Маршрут2 (AD) ---"
log string "A->D: " >> AD >> " км | " >> time_ad >> " мин"
log string "Итого: " >> total_route2 >> " мин"

? Сравнение их
if (total_route1 > total_route2)
    log string "Вывод: Маршрут 2 быстрее на " >> (total_route1 - total_route2) >> " мин"
else
    log string "Вывод: Маршрут 1 быстрее на " >> (total_route2 - total_route1) >> " мин"
close

finish
