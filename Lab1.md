            САНКТ-ПЕТЕРБУРГСКИЙ НАЦИОНАЛЬНЫЙ ИССЛЕДОВАТЕЛЬСКИЙ УНИВЕРСИТЕТ ИНФОРМАЦИОННЫХ ТЕХНОЛОГИЙ, МЕХАНИКИ И ОПТИКИ 
                                       ФАКУЛЬТЕТ ИНФОКОММУНИКАЦИОННЫХ ТЕХНОЛОГИЙ 
    
                                Отчет по лабораторной работе №1 по курсу «Информатика»



 

                                              
                                                                                              Выполнил:
                                                                                              Буй Тхук Хуен - К3139
                                                                                              Проверила:
                                                                                              Александрович A.У.


                                      
                                                   Санкт-Петербург
                                                        2024 г.

   ### Задачи по варианту

1.  Создайте новый файл с именем script.bash

 touch script.bash

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeg5FSw948dglnP1ZLWnNv_LFBu3v598UDeZ0wvUKmxhV2100xZpTTx5oqDNbU4t-b8ZmqS1yc_sNipRcNf5q5Ri5kIEDS4ofEun4cdz5KS15zWVLBRlDRWWFIiIG1XAPAZo7H8NG9IF7lQd335tc2kEj0P?key=4MZEUnrZXkmmpMWe1RnVrQ)

-   Открываю терминал с помощью комбинации клавиш Ctrl+Alt+T.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcXOP15yHF6qfF0H3aaJ5dQgskpyAu_QTqSi5CYq9ytyxKUDu6blFqeQjyPaqbZJrngMFhIH-dQoWyrZJO4Dt1a18Hv6uDAhsnY-0AeBbZBn7uPL3IzxW4KJJLMT24xjKAOdLTq0543FdjEDT35Hx4X13N7?key=4MZEUnrZXkmmpMWe1RnVrQ)

-   Пишу команду touch script.bash чтобы создать пустой файл с именем "script.bash".

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXexD96xE9vJC6qQo_oFI775QWRvHCo4uD2YM7aI_QhdvqLPkWPsL5sVUDD_Ra3LK5ha9X6neGKsbkuT9qdyaOfWptzzsMKfE-nnoOp4d2Q-eATYQ9R5UCKI7phDT6dC-BgNtIgPhfOIdYBO-RtOrhiBKKZK?key=4MZEUnrZXkmmpMWe1RnVrQ)

-   Использую команду ls, чтобы проверить, создан ли файл или нет.
2.  Откройте созданный файл script.bash для редактирования. Стандартный текстовый редактор в Linux Ubuntu это gedit. Выполните в терминале

 gedit script.bash

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcAQLqNSUA9rZBWVP0cMXXzlVBq_uo6FAEt6nN6btIOf_Q4tvTS6QA0NkXkw7t6scF2UHNnqTSeXX4lx_onwycQywiNX2PAdoP9dGuTPwL8Qqj6mxXAHQP2oQCo_8d8pm3s5o_QBLCV2kW_7iG4JQirSw6c?key=4MZEUnrZXkmmpMWe1RnVrQ)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdHCv86f4Z5U0k_IPWGPFxoHTxNIerfl1V4FaQ53qWfNmDcFnU3XI3MMwTiqVKNEdV4LOTe8DGDNU-goZkfHeNW7_jeSBunwbkGx0Krhf0xDcePtBQakJqz9J_dlj4R1THvpZLvue_Cy1YTcOl5LBj5r6I?key=4MZEUnrZXkmmpMWe1RnVrQ)

-   Пишу gedit script.bash чтобы открыть недавно созданный файл "script.bash" в графическом текстовом редакторе под названием "gedit".
3.  Впишите следующий скрипт

 #!/bin/bash

 echo "Welcome to ITMO University"

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXevNG1zfXes8X2MjM2FRnZUy5EfmehLdssS_gbd7IlU3-WEvQE3x6MoVpx_56AhaQi2op1Kc_R0z8VlrX7UxkwN79HaPn1OVaZEUEgZoL2Emern49lU4_gf3blSw-OVogpXpwesGz7d19TkXh-93KJhk7s?key=4MZEUnrZXkmmpMWe1RnVrQ)

-   Записываю скрипт в файл
4.  Сохраните файл. Закройте текстовый редактор gedit. Запустите bash-скрипт, выполнив в терминале

 bash script.bash

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdsxL6V6d8xE31IpS-wD3qOGdFaeNNNskWvibI1QtWtrQT1MXUsnRGIc19D1sjlQeieRV0JWSKT6xQpjxTY6M3rbBpzw970gp_NmQ7Y42YWZd9hs4PKFa_gpTgLUnZ0QMuln-9_Ui7P27af3fWdHgFplb98?key=4MZEUnrZXkmmpMWe1RnVrQ)

-    Пишу команду bash script.bash, затем нажал Enter.
5.  Если вы все сделали верно, то в терминале должна отобразиться строка Welcome to ITMO University. А теперь, используя знания полученные из лекций, дополнительных источников и, добавив к этому немного смекалки, решите следующую задачу.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfRxddmh-VGz1tcFQQ3CbRz3GMF2WOm825edLcLb6F7_TuRPs6VWDRrX4tBjSSVix6uWDIIYXsKV7p5IZC3N32Zl4CJQ8QVyqQPtTJRwaI2ZAkeWwz2A1CEBpTuKBvvImogdck9YdAAZQdSD_pk6UzQcbMl?key=4MZEUnrZXkmmpMWe1RnVrQ)

### Задача:

Модифицируйте файл script.bash так, чтобы при его запуске в терминале в виде

 bash script.bash Vasya Pupkin

Вывод был: Welcome, Vasya Pupkin

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfFShFcwu39A4lB0MWj-H08b97EflVAIjVUPVjzo1gjGIjVuuAN-SPZTkuYavjgoidFCEjTH3UExk5sRQQeIg61pNTc9xkHDcCuuBdxS6--_R5jZoIjx74Kuh-FEN-Y8dVMVZjz_I1fsLgqtnPsOy_GPCab?key=4MZEUnrZXkmmpMWe1RnVrQ)

-    Открываю файл с помощью команды gedit script.bash, изменив сценарий на “Welcome, $\*”. Использование $\* гарантирует, что все аргументы будут включены в вывод.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe2CwiLs0HV_E9pSBoDT9J7qIp7MPSMpSYnzWq16oEJklrKEBvHZLRzedMWHbtxS6D9JENJcqEXSQhTCxogEz5TJI0MRWX0m5OFtK6wyfjgL_cS0K4a2qfDT_9MwQEsJQ3kJgm_iIl-S9Z_WFkZZVV6fMnX?key=4MZEUnrZXkmmpMWe1RnVrQ)

-   Открываю терминал и написал команду bash script.bash Vasya Pupkin, затем нажал Enter.
