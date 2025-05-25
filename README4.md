?есть 4 числа a, b, c, d, гарантируется, что a > b > c > d, задаётся число x, выведите логичкое выражение, между какими 2 переменными находится x или он меньше всех / больше всех. ответ в формате b > x > c и т.п. - отправьте ссылка на ваш репозиторий

start
? Объявление переменных (пример значений)
new a number
set a 50    
new b number
set b 40
new c number
set c 30
new d number
set d 20
new x number
set x 34     ? наш тот самый легендарный х

? Определяем положения x на карте с 4 точками, с которых готовилось нападение))
if (x > a)
    log string "x > a"
else
    if (x > b)
        log string "a > x > b"
    else
        if (x > c)
            log string "b > x > c"
        else
            if (x > d)
                log string "c > x > d"
            else
                log string "x < d"
            close
        close
    close
close

finish
