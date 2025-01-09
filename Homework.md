                                    САНКТ-ПЕТЕРБУРГСКИЙ НАЦИОНАЛЬНЫЙ ИССЛЕДОВАТЕЛЬСКИЙ УНИВЕРСИТЕТ

                                            ИНФОРМАЦИОННЫХ ТЕХНОЛОГИЙ, МЕХАНИКИ И ОПТИКИ

                                             ФАКУЛЬТЕТ ИНФОКОММУНИКАЦИОННЫХ ТЕХНОЛОГИЙ

                                                                           
                                                                           
                                                   Отчет по домашнему заданию

                                                     по курсу «Информатика»

                                                 Тема: Планировщик задач cron





                                                                                                                              
                                                                                                                              
                                                                                                      Выполнил: 
                                                                                                      Буй Тхук Хуен К3139
                                                                                                                          
                                                                                                      Проверила:
                                                                                                      Владимировна Б.Е.

                                                                    


                                                                    
                                                      Санкт-Петербург
                                                          2024 г.


## Задачи 

### Заказы продуктового онлайн магазина.

В качестве исходных данных выступает файл orders.csv, представляющий собой список заказов. Файл состоит из набора строк с колонками, разделенных между собой точкой с запятой.

Каждая строка содержит информацию о заказе продуктов в формате:

<Номер заказа>;<Набор прродуктов>;<ФИО заказчика>;<Адрес доставки>;<Номер телефона>;<Приоритет доставки>

Каждая колонка о заказе имеет свой форматно-логический контроль:

- ___Номер заказа___ - пятизначное число. Поле не может быть пустым.

- ___Набор продуктов___ - перечисление наименований через запятую с пробелом (могут повторяться).
- ___ФИО заказчика___ - в формате: **_<Фамилия> <Имя> <Отчество>_**.
- ___Адрес доставки___ - адрес состоящий из шаблона: ___<Страна>. <Регион>. <Город>. <Улица>___. Например: (Российская Федерация. Москва. Москва. Новокузнецкая). Поле может быть пустым (_является ошибкой_).

- ___Номер телефона___ - по шаблону: **+x-xxx-xxx-xx-xx**, где x - любая цифра 0-9. 
- ___Приоритет доставки___ - перечисление **MAX, MIDDLE, LOW**.

### Необходимо
1. Фильтрация и экспорт заказов с адресами в России и сохранить в файл russian_orders.txt
2. Фильтрация и экспорт заказов с правильным форматом номера телефона +7-XXX-XXX-XX-XX и сохранить в файл valid_orders.txt
3. Сортировать заказы по приоритету от MAX, MIDDLE, LOW и сохранить в файл sorted_orders.txt
4. Подсчитать количество появлений каждого типа продукта и сохранить в файл quality_orders.txt

### Пример входных данных

31987;Сыр, Колбаса, Сыр, Макароны, Колбаса;Петрова Анна;Россия. Ленинградская область. Санкт-Петербург. набережная реки Фонтанки;+7-921-456-78-90;MIDDLE

87459;Молоко, Яблоки, Хлеб, Яблоки, Молоко;Иванов Иван Иванович;Россия. Московская область. Москва. улица Пушкина;+7-912-345-67-89;MAX

31987;Сыр, Колбаса, Макароны, Сыр, Колбаса;Петрова Анна Сергеевна;Франция. Иль-де-Франс. Париж. Шанз-Элизе;+3-214-020-50-50;MIDDLE

56342;Хлеб, Молоко, Хлеб, Молоко;Смирнова Мария Леонидовна;Германия. Бавария. Мюнхен. Мариенплац;+4-989-234-56;LOW 

48276;Яблоки, Макароны, Яблоки;Алексеев Алексей Алексеевич;Италия. Лацио. Рим. Колизей;+3-061-234-56-78;MAX

65829;Сок, Вода, Сок, Вода;Белова Екатерина Михайловна;Испания. Каталония. Барселона. Рамбла;+34-93-1234-567;LOW 

72901;Чай, Кофе, Чай, Кофе;Михайлов Сергей Петрович;Великобритания. Англия. Лондон. Бейкер-стрит;+4-207-946-09-58;LOW

84756;Печенье, Сыр, Печенье, Сыр;Васильева Анна Владимировна;Япония. Шибуя. Шибуя-кроссинг;+8-131-234-5678;MAX 

90385;Макароны, Сыр, Макароны, Сыр;Николаев Николай;;+1-416-123-45-67;LOW 

---
## Ход работы
### Входные данные в *orders.сsv*:
```
87459;Молоко, Яблоки, Хлеб, Яблоки, Молоко;Иванов Иван Иванович;Россия. Московская область. Москва. улица Пушкина;+7-912-345-67-89;MAX
31987;Сыр, Колбаса, Макароны, Сыр, Колбаса;Петрова Анна Сергеевна;Россия. Ростовская область. Ростов-на-Дону. проспект Кировский;+7-863-123-45-67;MIDDLE
56342;Хлеб, Молоко, Хлеб, Молоко;Смирнова Мария Леонидовна;Россия. Бавария. Мюнхен. Мариенплац;+7-495-123-45-67;LOW
48276;Яблоки, Макароны, Яблоки;Алексеев Алексей Алексеевич;Россия. Краснодарский край. Сочи. улица Ленина;+7-918-123-45-67;MAX
65829;Сок, Вода, Сок, Вода;Белова Екатерина Михайловна;Россия. Татарстан. Казань. проспект Победы;+7-927-654-32-10;LOW
72901;Чай, Кофе, Чай, Кофе;Михайлов Сергей Петрович;Россия. Челябинская область. Челябинск. улица Ленина;+7-351-123-45-67;LOW
53975;Печенье, Сыр, Печенье, Сыр;Васильева Анна Владимировна;Япония. Токио. Сибуя;+81-3-1234-5678;MAX 
32864;Макароны, Сыр, Макароны, Сыр;Николаев Николай;Россия. Самарская область. Самара. улица Фрунзе;+7-846-123-45-67;LOW
31987;Сыр, Хлеб, Яблоки, Колбаса;Сидорова Мария Александровна;Россия. Краснодарский край. Новороссийск. набережная;+7-8617-123-45-67;MIDDLE 
56397;Кофе, Чай, Сахар, Кофе;Кузнецов Алексей Викторович;Россия. Республика Татарстан. Казань. улица Баумана;+7-843-1234-5678;MAX
63076;Рис, Бобы, Овощи;Петров Сергей Петрович;США. Калифорния. Лос-Анджелес. Голливудский бульвар;+1-213-555-12-34;MIDDLE 
12385;Мясо, Картофель, Мясо;Иванова Ольга Сергеевна;Россия. Москва. Арбатская улица;+7-495-9876-5432;LOW 
47297;Салат, Огурцы, Помидоры;Александрова Наталья Васильевна;Германия. Берлин. Бранденбургские ворота;+49-30-12345678;MAX 
68393;Пиво, Вино, Вода;Смирнов Игорь Николаевич;Испания. Мадрид. Площадь Испании;+34-91-234-56-78;LOW 
42754;Кекс, Пирог, Кекс;Морозов Василий Иванович;Италия. Флоренция.;+39-055-1234567;LOW 
57382;Чипсы, Попкорн, Чипсы;Федорова Екатерина Андреевна;Великобритания. Лондон.;+44-131-1234567;MAX 
46812;Паста, Соус, Паста, Овощи;Никитин Дмитрий Сергеевич;;+1-416-76543--21;LOW 
85214;Курица, Рис, Специи;, Александрова Ирина Владимировна;Россия. Московская область. Подольск.;+7-495-876-54-32;MIDDLE
96231;Огурцы, Помидоры, Перец;Григорьев Степан Андреевич;Россия. Республика Башкортостан. Уфа. улица Ленина;+7-347-123-45-67;MAX
27456;Молоко, Хлеб, Яблоки;Павлова Ольга Николаевна;Россия. Санкт-Петербург. Невский проспект;+7-812-234-56-78;LOW
38412;Бананы, Яблоки, Груши;Коваленко Игорь Анатольевич;Россия. Новосибирская область. Новосибирск. улица Красный проспект;+7-387-123-45-67;MIDDLE
29476;Чай, Кофе, Сахар;Дмитриев Андрей Сергеевич;Россия. Республика Татарстан. Казань. улица Баумана;+7-843-765-43-21;MAX
84756;Печенье, Шоколад, Конфеты;Лебедева Наталья Сергеевна;Франция. Париж. Елисейские поля;+33-1-73-55-67;LOW 
56432;Спагетти, Соус, Паста;Тихонов Сергей Александрович;Италия. Рим. Ватиканская площадь;+39-06-12345678;LOW 
67890;Фрукты, Овощи, Орехи;Захаров Алексей Викторович;Россия. Краснодарский край. Краснодар. улица Красная;+7-861-23456789;MIDDLE 
78234;Кефир, Йогурт, Творог;Сидорова Анна Викторовна;Россия. Санкт-Петербург. Набережная реки Фонтанки;+7-812-98765432;MAX 
```
1. Фильтрация и экспорт заказов с адресами в России и сохранить в файл russian_orders.txt

    Используем команду, чтобы фильтровать и экспортировать заказы с адресами в России в файл russian_orders.txt:
    
    ` grep "Россия" orders.csv > russian_orders.txt `
   
   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf5YHE079JBld7CBpoN3jnutMgvQeeZ91x4eIZvfXEMVr-Z3ioZh8tCMgP8RFbC-X1X57RU_l7CThWCG9Gu-Bbt033JhEYjUVueWjYZNYoBxg1JFqGwEi09OpLDRYQiFeJ2sbczXg?key=kidet-S8y_Gc6FaGghN_mTwZ)

    Используем команду, чтобы проверить файл: 

    ` cat russian_orders.txt`

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdIFVjX-QFC7cqhtuoKNF8O4Yr-WbsEgNiex6EHBtC5t-4rLXmP1GiUXq2TNsRK8KqKIBxFX4NkEopWdCmJ6TK-aH9kQOGpobEi8cWKO7BuEq19NgkRSuR8IzfuILMkogxLW9JH8Q?key=kidet-S8y_Gc6FaGghN_mTwZ)

3. Фильтрация и экспорт заказов с правильным форматом номера телефона +7-XXX-XXX-XX-XX и сохранить в файл valid_orders.txt
    
    Используем команду, чтобы фильтровать и экспортировать заказ с правильным форматом номера телефон

    ` grep '^\+7-[0-9]{3}-[0-9]{3}-[0-9]{2}-[0-9]{2}' russian_orders.txt > valid_orders.txt `

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdhQrJlaZtBURDk_Dl0J4ivMZ-LuNLWiB4a5CAkdtZ59y_GKaujaT8vCpEPpVLHISmhK0FpV4wC8DIjuhhig8bENryqSVUvLD5So3t-3QllLv4W_0pbpUUX4mpyDS4XGmwxOUPB?key=kidet-S8y_Gc6FaGghN_mTwZ)

    Используем команду, чтобы проверить файл:

    ` cat valid_orders.txt `

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd6RO-nq4bQUlxJtptC7NsxXEZ8hy1hDfFBba1Kpv14oQsNE1dKdQEyUC_LfYy4DGJV6sKFoaPApwEinc0cd8BkpfUlSrpN9gH0jpk-u18_RQ2iirqs9W_uQhbhLZHHowjivYN3-g?key=kidet-S8y_Gc6FaGghN_mTwZ)

5. Сортировать заказы по приоритету от MAX, MIDDLE, LOW и сохранить в файл sorted_orders.txt

    Используем команду, чтобы cортировать заказы по приоритету от MAX, MIDDLE, LOW

    ``` 
    grep ";MAX" orders_advanced.csv > sorted_orders.txt
    grep ";MIDDLE" orders_advanced.csv >> sorted_orders.txt
    grep ";LOW" orders_advanced.csv >> sorted_orders.txt
   ```

    Используем команду, чтобы проверить файл:

    ` cat sorted_orders.txt `
   
   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeSdfH_vUXiPjzYM3NwGeKPB9NV3qctwvEGzTm53MArr7aEwx43BpnSlnJEGVH4f8fEnFCz5k1u14LSZuQy00Zs3pUjRaUx-10tO2TktvMi_nM62_mGSGUvhVhDctTzFapMIKeh?key=kidet-S8y_Gc6FaGghN_mTwZ)

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdrAmIFlFFUP4wHxeAJc6Kv6rGL6YwT2GHZLtoe_LcJPVrpRl8spxTgd8_bN5h62QdL_MxZWfwVAveNOh5yueTyp8aYzt7_c6F-rdAJiF4a3z03CpSUYAupyv_HM2eNnJEgGLayUw?key=kidet-S8y_Gc6FaGghN_mTwZ)

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdPjULjSrnQDA8ue5otJj2b9ZTyXaks8b72sTQa1xyV2RA9aOjPafxFKlP0-RksgCvMu_2G0ibaq78XDZTnwHDL-FGnIRvkVnUCrf7mT05sAJ2wpo3JhuNjsZaYe9t4QfL7AhsG3A?key=kidet-S8y_Gc6FaGghN_mTwZ)

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXea0WTan3AmFGJyxJbadJ5E_K2UlfAeUNQmkLoUEX3NHil_ATYorKA2cNjInkRN0BwjlhxL5A1phEjLtEd3JayJrgp6EA8e9sxpjsnbzJhfMdW4TKW9Zz-jioZLd8Hi13P0cDjyMg?key=kidet-S8y_Gc6FaGghN_mTwZ)

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdwK_Uk9EPDVgWT-CjaemG-IOU0KJXLD-G6JVIEbMYnqMle2A34kOv0iQoMRln1t77JgJIa2hKJqIshs3zW8doJvrqCEIEkewzRbbDTaP42MoR3LSUrEWI4gg9i35T_41CI9qBRmQ?key=kidet-S8y_Gc6FaGghN_mTwZ)

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfrhoA4dwmS33X8EteX2NPQ8OVWsTyhlcENvXAmE4K0ZC7xEGkEKIKQk7JkiqmDdMiB29CFvuHI2K2pDwR-8IhzfjoOEzxi61QyjhmdC0n7v9BRvMln4KMXXDpKhWcUS0Q6Q5DBlw?key=kidet-S8y_Gc6FaGghN_mTwZ)

7. Подсчитать количество появлений каждого типа продукта и сохранить в файл quality_orders.txt

    Используем команду, чтобы подсчитать количество появлений каждого типа продукта

    ` grep -oE '[^;]+, " sorted_orders.txt | tr -d " " | tr "," "\n" | grep -v '^$' | sort | uniq -c | sort -nr | awk '{print $2 ": " $1}' > quality_orders.txt`

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfBJ1P_JtyXzAuExcRKF04b9WdgJk07J_i3qsWAvtGx9nf_5XniD8TabuA0ntG7UHidiL6vV7q-mTCVzwYwDk9qPUxP6zYC0FD_j5nLNW5bK_c5Xpz70WBGjgyRDM_KKHDBzAW6Sw?key=kidet-S8y_Gc6FaGghN_mTwZ)

    Используем команду, чтобы проверить файл:

    ` cat quality_orders.txt `

   ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd0hnKlcMmiKCm6UGTYgMtMnZH6D5_hWq4jQmnuiMOb6UtNzbsfuE6YnYbU7S0KNUokNauW8lkkQYCEybFTW9ndKKYdhV_3AGtS_Uw_YJageeshWwQlUdqAmOA0tO5i8UiwclMkJw?key=kidet-S8y_Gc6FaGghN_mTwZ)

---
## Источник
- [Команда Grep в Linux](https://zomro.com/rus/blog/faq/509-grep-command-in-linux)
- [Selectel Academy - Команда Grep в Linux ](https://selectel.ru/blog/tutorials/grep-command-in-linux/?form=MG0AV3)
- [Руководство по команде grep в Linux](https://wiki.merionet.ru/articles/rukovodstvo-po-komande-grep-v-linux?form=MG0AV3).
