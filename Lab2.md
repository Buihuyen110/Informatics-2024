
                           САНКТ-ПЕТЕРБУРГСКИЙ НАЦИОНАЛЬНЫЙ ИССЛЕДОВАТЕЛЬСКИЙ УНИВЕРСИТЕТ

                                    ИНФОРМАЦИОННЫХ ТЕХНОЛОГИЙ, МЕХАНИКИ И ОПТИКИ

                                      ФАКУЛЬТЕТ ИНФОКОММУНИКАЦИОННЫХ ТЕХНОЛОГИЙ

                                           Отчет по лабораторной работе №2

                                                по курсу «Информатика»

                                                                                          
                                                                                          
                                                                                          
                                                                                          
                                                                                          Выполнил: 
                                                                                          Буй Тхук Хуен - К3139
                                                                                          Проверила:
                                                                                          Владимировна Б.Е.

                                                 
                                                 
                                                 
                                                 Санкт-Петербург

                                                     2024 г.

## Задачи по варианту

1.  Открываю терминал с помощью комбинации клавиш Ctrl+Alt+T.

Создаю  новый файл с именем ip\_to\_binary.bash

touch ip\_to\_binary.bash

Использую команду ls, чтобы проверить, создан ли файл или нет.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeMaWh-mA0IxAJejbkFZuD7iNH-vQvJEOuqE9qxOPNc42xWFwHlwULhugdNYZMP_e_JgjsIq0KS7RQxQZGWU7nQOlCfqd8HFTxIad8JyasIDpMTgiEv4Bjcfz0hG3OClo2p-lnlNNg0_oDEJDeqFAKk0JBC?key=xnfKaIuyDKowxBhOp7dZog)

2.  Открываю созданный файл ip\_to\_binary.bash для редактирования. Стандартный текстовый редактор в Ubuntu это gedit. Выполню в терминале

 gedit ip\_to\_binary.bash

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdufOf-phKOfPdJSvuc2RyeCS6iav3j9PCc6XlnMGfk4Njz2rpiDjaHCFvj7USlRUaO3mSFUD5rdfZaZoTYFshCZ4kzspiE32t1T9Kxt8Z7ux-SfeuQ5PNXoVvF9SLds96WvQaPzeYGcWhYYFRIPHb__zA?key=xnfKaIuyDKowxBhOp7dZog)

3.  Напишу скрипт, который на вход принимает IPv4-адрес в десятичном формате, а на выходе обеспечивает данный IP-адрес в двоичном формате.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcLRCY6gYnbcm9ReVT-fItOLZbqAm_mVOwo_mdo-6APp-Bmw6BUBipQGObHmM2mFYVqi1ARHJesiDT0uGGE-BPytGjG0heSSjuftV5rtSb88UiCXHJQtGA6mJkZ3ThS13LrhvLrcaGjoDp3f9UdUe-EwT1b?key=xnfKaIuyDKowxBhOp7dZog)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdABYtiJ4VQ-e7d2qfBKHERI_LVpFtHMe6iDyaVV1X3edDqNwG2tDEB91OTqIR2-g-YGTx2voz5epx10T5L6UYeR6afveIoRMLnJDoGBC8An4tCZwjgGH37CAHAqFY3cPiEwiFZdY0Gev6Yg6-k1AjFtvEC?key=xnfKaIuyDKowxBhOp7dZog)

- Функция проверки IP-адреса: проверяет, является ли предоставленный IP-адрес допустимым.
     + оператор if использует регулярное выражение для проверки того, соответствует ли ввод шаблону адреса IPv4 (четыре октета, разделенных точками).
     + разбивает IP-адрес на октеты и проверяет, находится ли каждый октет в диапазоне от 0 до 255, возвращает 0 для допустимого IP и 1 для недопустимого.
-   Функция преобразования IP-адреса в двоичный код: преобразует допустимый адрес IPv4 в его двоичное представление.
    + Подобно функции проверки, она использует IFS для разделения IP на четыре октета.
    + Команда bc используется для базового преобразования, преобразуя каждый десятичный октет в двоичный.
    + Команда printf форматирует двоичный вывод, чтобы обеспечить наличие начальных нулей (8 бит).
    + Каждый двоичный октет конкатенируется с разделителем в виде точки (.).
    + Завершающая точка удаляется перед возвратом окончательной двоичной строки.
-   Пользовательский ввод и проверка: Запрашивает у пользователя IP-адрес. Вызывает функцию validate\_ip для проверки допустимости ввода. Если ввод недопустим, выводит сообщение об ошибке и завершает работу с кодом состояния 1.
-   Вызывает функцию ip\_to\_binary для преобразования допустимого IP-адреса в двоичный формат. Выводит полученный двоичный адрес.

4.  Использую  команду chmod +x ip\_to\_binary.bash, чтобы сделать исполняемый файл. Затем я запускаю код: ./ip\_to\_binary.bash

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc0jf2H7hLfznmCl5B8ht0UdBtVULtWD3ffJ5jt46NV6tppW8zjm0zX3PLyQaettEY_1nQF4dZ5-LYiipUCSzJF4EeJGVjJQPEtEI-DvHHELY4Y3-2GyJJWfkw2EI_Q5q-n8aCTuSn6kfMUB8taXKMqjobV?key=xnfKaIuyDKowxBhOp7dZog)

5.  Ввожу данные. Нажму Enter

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeg-4yHKuBTWBuUfb7AxcNPxGCXc0IDFriOf0-GaYJH2juiqTgKQD6sSfW7qOR5wN-NoFeVUlxiRu2yithuqovj0iGTves-8YqNYR3HcRZv4TzyuAtH_3BwEtW2mh5t1HTh1OPnfuQpf19swwRbBJCm1IQ?key=xnfKaIuyDKowxBhOp7dZog)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcXHAfamdfbllHGePwIlPjroeMjYp2Cocqwyo_XkhW9IfUaNYn_IW_bETr7alRjYj9VUTwNXJFXrSePsg3-U9tNFJn8PlguhgRTZfzWmcHMXULPiThEyKSWzCYNz_k3lcIo3BaSpy47arbpkmCBM3X4Zu-_?key=xnfKaIuyDKowxBhOp7dZog)
