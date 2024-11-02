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


#Задачи

Необходимо настроить виртуальную машину А с Ubuntu (желательно, но можно и другую Linux подобную ОС) в VirtualBox. Обеспечить доступ в сеть Интернет. Осуществить проверку этого доступа и приложить скриншот из терминала. Следующим шагом настроить ещё одну виртуальную машину Б. После чего обеспечить сетевой доступ от машины А к машину Б. Приложить скриншот из терминала. Поднять ещё одну виртуальную машину В. Организовать сетевой доступ:

1.  из машины А в машину Б,
2.  из машины А в машину В,
3.  но запретить доступ из машины Б в машину В,
4.  приложить скриншот, на котором видно терминалы всех трёх машин и видно что между машинами есть (или нет) доступа.

#Решение

1.  Настроила виртуальную машину А (serveA). Обеспечить доступ в сеть Интернет.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc-6mNidGXZUUv_6hRkUa6yBc6qWZaYY7sOpsQCFVjKcKDGaP5mI24Abarj7hJJ0UdEm4KfeXsbSJjiAE9V8F87svBJD2nGPY4UhX2BeMElYS9XqgqD1ENzS2xnVVTp69Sf8GEoxi5bBcqsAL6W9p2H-eM?key=-Izx9FaWW9Tn5ziZQGDIQaMG)

2.  Настроила виртуальную машину Б (serveB). Обеспечить доступ в сеть Интернет.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXddwmIjCIRp5wfXYUUDInq7b14DR-RdAGKKtQQRyt-wOo-k5514tZEYwCKz_vrmBIWZGkGH24jbwoh8rFkXOxiHFS266jG2xhlQvpuxf4AB95S59W6ZtPUtVQpeiQFTVaPa5NmSNlcjR96DlQkzWPh5I3Va?key=-Izx9FaWW9Tn5ziZQGDIQaMG)

3.  Обеспечила сетевой доступ от машины А (serveA) к машину Б (serveB).

Использую command:  ping <IP-адрес машины Б>

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdbqxCaRo8QEn3dbIVa0HLQzKcYweOtsXlN_fP91SxK1M-7D3TF1drLEXSc9476DMx0FQys5BsyKNAv67TTv0OTqJcXG3aZnaOlb2CLDt2HZbUBq4YS5Zw24I_-atQKbDiG2CSwCDzbIRtXXTdwrD8uBo8?key=-Izx9FaWW9Tn5ziZQGDIQaMG)

4.  Настроила виртуальную машину B (serveC). Обеспечить доступ в сеть Интернет.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdjJiy0wtiviYJJDYhbeoEHcY_NVVH11Ov5d_tMN2zHL0K6cDFg8ecHkQaFtrSZ1etf1r-dVYnVVKJU8Ndlfg0BoE0__GQO_jYpC6iyy_fnVPNK6nArHoLW-rFyGUoxzTsNkfUQZ9Uu-zeceeLVT_3OpIu8?key=-Izx9FaWW9Tn5ziZQGDIQaMG)

5.  Обеспечила сетевой доступ от машины А (serveA) к машину B (serveC).

Использую command:        ping <IP-адрес машины B>

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfhS-TTHIqGuYhJ72z17MWVZIMcXM09jpHlAMzGmdiprf5Phu22eyf2zTXk8q2ZWJZa8AAl4qKbNZ1Z1NLDwPrfps6nXKKnKMkw2ChhxpontE06UZjuiV729SEGfBO3XHOmosnpRZSpz92djwk7yNI8oeU?key=-Izx9FaWW9Tn5ziZQGDIQaMG)

6.  Запретила доступ из машины Б (serveB) в машину В (serveC)

использую command:

       sudo iptables -A OUTPUT -d <IP-адрес машины B>

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfBTknWUtcv5cC-QLG5cSzCwNAiRf81gJYOOu0Xbh62CJliljo3xbcqRh4VDQcIsPtTsToTU_y5hZxhGupjt822X8tQoRhqpoLLbTOBBF3TMGYcANxpaobDgv38PaNZOQLMePdDYjAviHFNgX7KjLafiRDX?key=-Izx9FaWW9Tn5ziZQGDIQaMG)

7.  Результат: из машины А в машину Б, из машины А в машину В, но запретить доступ из машины Б в машину В,

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfAFlIgVtnqbO1Vqnbx3I9xWfWIcRqbIf7rOiT4Jjd4_jwamIOF6aZ2O1jMo3miA-iE02ylEyJF4QVgpAHydk9iLRn-5DdcBJXKtm-E--4BKfOoOZhmerE-vCahgd0kFsDEizA-mYrZ5vpso1plrGdYd4uk?key=-Izx9FaWW9Tn5ziZQGDIQaMG)
