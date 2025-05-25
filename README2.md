?по такому же принципу определить, хватает ли нам денег чтобы купить какой-то товар

start
? Создание переменных
new product_price number
set product_price 1097 ? Цена товара (Cyberpunk сейчас)
new user_money number
set user_money 2067    ? Количество денег

? Расчет порога
new price_threshold number
set price_threshold product_price - 1

? Проверка возможности покупки
if (user_money > price_threshold)
    log string "Баланс: " >> user_money >> " руб(₽) / Цена: " >> product_price >> " руб(₽)"
    log string "Результат: Можно купить товар"
else
    log string "Баланс: " >> user_money >> " руб(₽) / Цена: " >> product_price >> " руб(₽)"
    log string "Результат: Недостаточно средств"
close
finish
