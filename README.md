# DSLogic_modding_with_Arduino
How to upgrade logic analyzer DSLogic U2Basic to DSLogic Plus with Arduino

Для тех у кого есть Arduino и паяльник ;)

Описание процедуры модификации на русском:
1. После манипуляций описанных в https://habr.com/ru/post/483496/ выпаиваем EEPROM с прошивкой
2. Ноги микрухи (в моем случае это была M24128-BW от фирмы ST) 1,2,3,4 и 7 соединяем вместе и паяем на GND 
   прошивающей схемы, в данном случае Arduino. Остальные пины к соответствующим пинам ины I2C.
3. Должно получится, как на фотке EEPROM connected to Arduino.jpg
4. Льем в Arduino скетч I2C_Flasher.ino, открываем терминал (я пользуюсь COM Port Toolkit 4.0), настраиваем на порт,
   куда подключен Arduino и стартуем наш скетч.
5. Скетч автоматом заменит нужные байты. Для пущей убедительности можно скопировать считанный Firmware в любой HEX редактор
   и сравнить с оригинальной прошивкой (они имеются в ссылках на https://habr.com/ru/post/483496/). У меня все получилось 
   (см. картинку DSLogic dump compare.jpg).
6. Паяем EEPROM обратно в анализатор (у меня получилось "кататак" DSLogic U2Basic after modification.jpg).
   Запускаем. Радуемся DSLogic Plus.
   
!!!Важно!!!
Все манипуляции выполняются на СВОЙ СТРАХ И РИСК. Автор данного материала за ущерб нанесенный оборудованию, имуществу, здоровью либо жизни ОТВЕТСТВЕННОСТИ НЕ НЕСЁТ.
!!!     !!!

Благодарности Авторам, материалы которых использовались:
Основной материал User420 https://habr.com/ru/post/483496/ - Браво, супер...
Неизвестный автор с HobbyTronics Ltd © 2020 http://www.hobbytronics.co.uk/arduino-external-eeprom - позаимствованы функции 
записи/чтения по I2C шине в скетче для Arduino
Даташит на EEPROM от ST Microelectronics - https://www.st.com/resource/en/datasheet/m24128-bf.pdf


