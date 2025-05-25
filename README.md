?напишите программу для определения, может ли человек купить алкоголь или нет. используйте переменную с возрастом, если человку 18 лет или больше, то он может купить алкоголь, иначе - нет

start
? Создание переменных
new adult_age number
set adult_age 18
new user_age number
set user_age 17

? Вычисление порога для алкоголизма
new age_threshold number
set age_threshold adult_age - 1

? Проверка возраста для начала жизни алкоголика
if (user_age > age_threshold)
    log string "Возраст: " >> user_age >> ". Можно купить алкоголь"
else
    log string "Возраст: " >> user_age >> ". Нельзя купить алкоголь"
close
finish
