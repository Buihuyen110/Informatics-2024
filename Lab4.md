                                           САНКТ-ПЕТЕРБУРГСКИЙ НАЦИОНАЛЬНЫЙ ИССЛЕДОВАТЕЛЬСКИЙ УНИВЕРСИТЕТ

                                                    ИНФОРМАЦИОННЫХ ТЕХНОЛОГИЙ, МЕХАНИКИ И ОПТИКИ

                                                     ФАКУЛЬТЕТ ИНФОКОММУНИКАЦИОННЫХ ТЕХНОЛОГИЙ

                                                                        
                                                                        
                                                          Отчет по лабораторной работе №3

                                                              по курсу «Информатика»

                                                                                                                                
                                                                                                                                
                                                                                                                Выполнил:
                                                                                                                Буй Тхук Хуен К3139
                                                                                                                                
                                                                                                                Проверила:
                                                                                                                Владимировна Б.Е.

                                                                           
                                                              Санкт-Петербург, 2024 г


## Задачи 

Запустить в контейнере приложение “aafire”. Обратите внимание, что оно бесконечное и контейнер не будет автоматически отключаться.  
Приложить скриншот в процессе работы контейнера.  

Далее в рамках лабораторной работы необходимо самостоятельно настроить сеть между двумя контейнерами, также как в предыдущей работе вы настраивали связь между двумя виртуальными машинами.  

Для проверки сети между контейнерами вам потребуется утилита ping. Поскольку контейнеры очень маленькие и в них нет ничего лишнего (по сравнению с виртуальными машинами) - ping там не установлен. В вашем образе нужно будет установить пакет с этой утилитой, помимо aafire.  

Далее запустите два контейнера с aafire и оставьте их в работающем состоянии.  
Откройте ещё одно окно терминала и создайте сеть при помощи команды 
```
docker network create myNetwork
```
После этого нужно будет подключить контейнеры к вашей сети. Названия контейнеров можно увидеть при выводе списка действующих контейнеров у вас на машине.
```
docker network connect myNetwork mycontainer1
docker network connect myNetwork mycontainer2
```
Теперь при помощи следующей команды вы можете увидеть настройки созданной вами сети.
```
docker network inspect myNetwork
```
Далее вам нужно самостоятельно протестировать соединение между контейнерами утилитой ping и приложить скриншот.

## Решение

1.  Создала Dockerfile для образа, который будет использовать приложение aafire. Открыла текстовый редактор и создайте файл с именем Dockerfile

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdtCzDnyvGWVe87ckaoWXktITwI9aKrOhrBjkNiQl_sXEFEzNphnfBY9W0OM_qES80V4Vc2tK17F7aTlSUg4EeO1YPnKFxIFAtI86SOVblfIrHFE6zkyTBz2SCIdKh6f5l7FZRKug?key=GE8snBIKeeSZ2a9WubhOQ6FK)

2.  Собрала образ с помощью следующей команды в терминале, находясь в директории с вашим Dockerfile:

```
docker build -t aafire-image .
```

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfdKQhFtQ2QlikSVGyPxpOOV_abDaPW4aFfqBKq6VTCYjXZae39hQqbFdsKQdhLI0URtbKFT-hoKBxZCQTksL77pDT60zsv3Wkr3Ru2EiUnKO4KF5UihWiPgy8CHXQ_DTSIJNjg?key=GE8snBIKeeSZ2a9WubhOQ6FK)

3.  Запустила два контейнера на основе созданного образа:

```
docker run -d --name aafire1 aafire-image
docker run -d --name aafire2 aafire-image
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQpjRIjKCfuI7wt6VkhCrZQMczXAVOColDAog1hER7eW9j4ntiY0uD9oSYJVpINoP0O8XkS3K32ghDHZDcmkhB9LpA1Phd0WW7nKTu7ZiuAS095jo1emknPoDprcGrclvZ6BQrpg?key=GE8snBIKeeSZ2a9WubhOQ6FK)

4.  Создала сеть для подключения контейнеров:

```
docker network create myNetwork
```

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfXTW8lzOG_kuvKSKVvNVaWvMeF_upDBa3IKrqxRy-dPYZlzgW_EMPJBDWmMiUlxK3AcVSm2surP7N0h17GGsCDvaIvtIN-QOOd1uPa96-MtQOQv_5Di09Moj9qJT12riAUnQ9wCg?key=GE8snBIKeeSZ2a9WubhOQ6FK)

5.  Подключила контейнеры к сети:

```
docker network connect myNetwork aafire1
docker network connect myNetwork aafire2
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeC1JnvgKe7MEUggfIUxQaYTRr7FVBlQUlyEfJ0-6hTRSmink8ggqX1Dgor_iTAP3q5pj4Jv7INwsv-sRvYEmh02tlhV1fBoRIOtnqjUp65l_wKnY-G9p-aK5B5mtq_mo34z7JP_A?key=GE8snBIKeeSZ2a9WubhOQ6FK)

6.  Проверила настройки сети:

```
docker network inspect myNetwork
```

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfwO3HUey04axn9AaXELCRx7_puPNc6IwxcEJHlOnsSGIyalkkPLM6_3A0ABu18zQe4-HTI2tlXREZgRUWXsrBl8x5WzidOonZiKEHGZq4tMXy4pRD4Xf4Zthj93KXBwpjP-OoCbw?key=GE8snBIKeeSZ2a9WubhOQ6FK)

7.  Открыла новый терминал и выполнила команду ping для проверки соединения между контейнерами:

```
docker exec -it aafire1 ping aafire2
```

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQ4qH5OYj79uthDEmBaRuqQLBzQuZCA8XGzupWSfh6EpsZChhP2zWkj_GAF3HCa21cyXOOKhLEpWpd3b5tmgQmarlo0zPutm1c1hXYUWv-6sLMQ7EO-kgKz6mGEINnEIo_aoo5pg?key=GE8snBIKeeSZ2a9WubhOQ6FK)
