# TRTPO-Project

# Требования к проекту

# 1 Введение

"Программирование ЭБУ автомобилей" - модуль предназначен для записи FLASH-памяти ЭБУ Bosch, через диагностический разъём.

# 2 Требования пользователя

## 2.1 Программные интерфейсы

Модулем поддерживаются следующие типы ЭБУ:

* (запись) Bosch EDC17C08

* (запись) Bosch EDC17CP14 (TPROT3) 

* (чтение/запись) Bosch ME(G)17.9.11/12/13 

* (чтение/запись) Bosch MED(G)17.9.8 (запись модифицированного ПО только в ЭБУ с отключенной проверкой подписи). 

Поддерживаемые форматы файлов:

* Несжатый BIN (BIN)

* Сжатый SMS-BIN (BIN)

* SMS-Container File (BCF)

* Дилерский формат прошивок GDS (BIN)

## 2.2 Интерфейс пользователя

Вкладка **FLASH**

рисунок 1

Вкладка содержит окно просмотра буфера программы контроллера и кнопок управления:

"Чтение" - чтение прошивки из контроллера во внутренний буфер программы.

"Запись" - запись прошивки из внутреннего буфера программы в контроллер.

Вкладка **Дополнительно**

рисунок 2

Вкладка содержит окно выбора опций работы программы:

**Дополнительные функции:**

Идентификация ЭБУ – позволяет запросить идентификационные данные ЭБУ

## 2.3 Характеристики пользователей

Целевой аудиторией данного приложения являются официальные сервисные центры. Допуск к работе с данным программным обеспечением имеют

специалисты-автодиагносты и автоэлектрики.

## 2.4 Предположения и зависимости

Для подключения ЭБУ к программатору используется кабель M74_CAN. При программировании ЭБУ M74_CAN обмен данными идет через адаптер 
J2534, который должен быть подключен к соответствующей колодке OBD-II на кабеле, при работе с М74 обмен идет по K-Line, адаптер 
подключать не нужно.
  
Подключение контроллера, снятого с автомобиля, возможно произвести универсальным кабелем Загрузчика.Для этого расположите ЭБУ на столе разъёмами к себе и произведите соединения с в соответствии с типом ЭБУ.

# 3 Системные требования

PC Windows 10/7/8/8.1

## 3.1 Функциональные требования

* Программирование ЭБУ может быть произведено без снятия с автомобиля, подключением к диагностической колодке. Обмен с ЭБУ происходит через интерфейс J2534, а не через адаптер загрузчика. Несмотря на это, адаптер загрузчика должен быть подключен к компьютеру для нормального функционирования ПО. Выбор и настройка адаптера J2534 производится в меню "Конфигурация"

* Для работы с ЭБУ, снятого с автомобиля, произведите соединения в соответствии с типом ЭБУ.
	
* Запись только калибровок при использовании нестандартного ПО или запись калибровок от другого ПО недопустима и может привести к необходимости восстановления ЭБУ модулем "BSL режим TC17xx (J2534)".
	
* При записи модифицированного ПО в ЭБУ ME(G)17.9.11/12/13 производится автоматическая подготовка калибровок для диагностической записи.
	
* Запись калибровок без ПО в ЭБУ MED(G)17.9.8 не включает проверку подписи.

* Запись модифицированных калибровок совместно с ПО в ЭБУ MED(G)17.9.8 не включает проверку подписи.
	
* Запись оригинальных калибровок совместно с ПО в ЭБУ MED(G)17.9.8 включает проверку подписи.

* Для сохранения прошивки в несжатом двоичном виде необходимо удерживать клавишу Shift при нажатии кнопки "Сохранить" в диалоговом окне сохранения файла.
	
* Для установки пароля на доступ к файлу необходимо удерживать клавишу Ctrl при нажатии кнопки "Сохранить" в диалоговом окне выбора имени файла.

## 3.2 Нефункциональные требования

### 3.2.1 АТРИБУТЫ КАЧЕСТВА

Возможность использования сохраненных прошивок без подключения к сети интернет.
