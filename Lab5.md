                                           САНКТ-ПЕТЕРБУРГСКИЙ НАЦИОНАЛЬНЫЙ ИССЛЕДОВАТЕЛЬСКИЙ УНИВЕРСИТЕТ

                                                    ИНФОРМАЦИОННЫХ ТЕХНОЛОГИЙ, МЕХАНИКИ И ОПТИКИ

                                                     ФАКУЛЬТЕТ ИНФОКОММУНИКАЦИОННЫХ ТЕХНОЛОГИЙ

                                                                        
                                                                        
                                                          Отчет по лабораторной работе №5

                                                              по курсу «Информатика»

                                                                                                                                
                                                                                                                                
                                                                                                                Выполнил:
                                                                                                                Буй Тхук Хуен К3139
                                                                                                                                
                                                                                                                Проверила:
                                                                                                                Владимировна Б.Е.

                                                                           
                                                              Санкт-Петербург
                                                                   2024 г


## Задачи 
1. Введение
2. Работа с ветками
3. Работа с удаленным репозиторием
4. Моделирование конфликта
5. Разрешение конфликта

## Решение
### 1. Введение
1. Создание репозитория на GitHub: 
    Создала новый репозиторий с именем practices
2. Клонирование репозитория:
   Открыла терминал и перешла в папку informatics, чтобы сохранить локальную копию репозитория
```
git clone <URL-репозитория>
cd git-lab
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdckbbL1WqMME3fm0iMzJ4x5hJuBcqKcbMNvhAmk3W3OT9ud7vsCIeutFnpcJaaLuMveyzoGNxVUBzNUfoxFrDDDrK9VFOweaBdKaBr-mRHhXho9SQlgp4h9Vlkk557l6JdrZq5-w?key=E5dHXVUTzknfca2XYtK_swaA)**
3. Добавление файла:
Создала новый текстовый файл example.txt, и добавила в него:
```
Welcome to ITMO university!
```

Вернилась в терминал и ввела:
```
git add example.txt
git commit -m "File added example.txt"
git push origin main
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXearoGRlvY0EfIDj5qAhog_AqqRC15xn1KjTS1Z2VSey7NdvGBXNAmrMRMngTTwMJ_AACZerRQ-a-Ycd3hOEKyPIzQVV9bMGOJKcm9Imtbkg2smjchceRcQfM43GYO7NZ1ZaYHz?key=E5dHXVUTzknfca2XYtK_swaA)**
4. Создание ветки: 
Создала новую ветку с названием feature-1, и переключилась на нее:
```
git branch feature-1
git checkout feature-1
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeLjrpP7HezGRS04JGPreHXOm_Hsw4uECJQ54b-9SRikD-xF0zGJLC3dJPkQ8BGz8ymk26T03RSFNCYxCfrXOKUTnQ2LEqTkXXikcnvAAdt-uJl0T0TjEL-LTfEdS4zMsQh_vLGZA?key=E5dHXVUTzknfca2XYtK_swaA)**
5. Отредактировала файл example.txt, добавив еще текст
``` 
Facylty Infocamunication of Technologies
```

6. Слияние изменений:
Переключилась обратно в основную ветку:
```
git checkout main

```
Слейте изменения из ветки feature-branch в основную ветку:

```
git merge feature-1
git push origin main

```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcMy1aILZhssCKHzIkwVar02R0JleWC82DDPIeHFb3ssKxboW1XE9JHQqknsGsr3x0E4WR6NECuMg_OmDBm_uFaboPOY_z16ujZaDxRGSG7nT2VMC0iGV4Fb5m38v5KduxJ232riQ?key=E5dHXVUTzknfca2XYtK_swaA)**
7. Завершение:
Проверила, что изменения успешно слиты и отображаются в основной ветке на GitHub. Завершила работу с репозиторием.

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdDVu-im02cAFTSXj5Vbe7ofn-PIiXA4r1_05g5Fmm1cRPQ4EyIXeUqvI3dA3bzXCnZOkD_K3SabZDbAOCxtAzKuSO-kXL_gY9l0pndmXhbWl3Of6dmuLFiiqFJP5MRCCk05GkYcA?key=E5dHXVUTzknfca2XYtK_swaA)**
### 2. Работа с ветками

1. Создайте новый текстовый файл с базовой структурой книги, например:

```
# Название книги

## Глава 1: Введение
Здесь будет введение в тему книги.

## Глава 2: Основы Git
Основные понятия и команды Git.

```

2. Создайте ветку "feature-login" для разработки новой функциональности:

```
git checkout -b feature-login
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe5xkDHf_xEeWCAhCneaSEij-EHf1LDieZ6ooUOSpwsrWsDwseA0_MAqkmkuUW0ZAoAA4ip1HpaPV9Ag2DHj9Kn32l6V0HG-TEudV6UzpQroOknGp6da-G1yr0aooIP4c0wvo6K_A?key=E5dHXVUTzknfca2XYtK_swaA)**
3. Внесите изменения в файл:

```
# Название книги

## Глава 1: Введение
Здесь будет введение в тему книги.

## Глава 2: Основы Git
Основные понятия и команды Git.

## Глава 3: Вход в систему
Раздел по новой функциональности входа в систему.
```

4. Завершите изменения, закоммитьте их и отправьте ветку на GitHub:

```
git add README.md
git commit -m "Добавлена глава 3: Вход в систему"
git push origin feature-login
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfbKYtkPvcGzsuswexs9J4aHTvRJlZcdZk_KjKe5zNYet64KPPjAt_c2wAOUXRaaoIpMbyVmn2Fp7sz5PkzUazj3sNqw8w_yP4ehwEb6EvU92g8avxn_1caFH7HiQfkRut71TtAqQ?key=E5dHXVUTzknfca2XYtK_swaA)**

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeuUaFTed73stSP0AE_LGSGsX4qrN99ot7lx9BSjsExjI64jG88oMUzZLkYhmgN91JIjHawa2gLUFa0vQrvlXgo1QbCQ1JGuHdOqFeUj3Q5i3PB5YpPsPYG8q-u6V3MGJeb-c_DYA?key=E5dHXVUTzknfca2XYtK_swaA)**

### 3. Работа с удаленным репозиторием

1. Переключитесь на основную ветку (main) и внесите изменения:

```
git checkout main
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcIcSz0ODRB9yHzkPkqWngUvtyUzxyozM2pdCaWMrxeuVxiozyZY8ESMk9Ij1K9_26-n7r4pr4WSAXA9COqRMFBnF-kSJBlrTK0WitHph93lTKMzSwxYnCaxkO8k_H_zcfa5-i9Dw?key=E5dHXVUTzknfca2XYtK_swaA)**

2. Внесите изменения в основной ветке (например, добавьте описание книги):

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git
Основные понятия и команды Git.

```

3. Закоммитьте изменения и отправьте их на GitHub:

```
git add <filename>
git commit -m "Изменено название книги и введение"
git push origin main

```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeDKfuNOCgj_dxYA-VUBmHBLadD1xEnlgNTJgT321QAeevhYRyOfHGCJKqfmmwupgsHJnmWX20mXJAMSxBvIUsmj0b7xyoIAvfHTp9ltvdZYfiAfz_hNEiwvhCl3pWc0T4LcA6PHw?key=E5dHXVUTzknfca2XYtK_swaA)**

## 4. Моделирование конфликта

1. Вернитесь в ветку "feature-login" и внесите изменения в том же участке:

```
git checkout feature-login
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf7StFC8X_U-rRY46h3i1hfb3b_Yx2Yh5tW66GuQXQ1wDCVEXUk4kaULOGKVR6CYsg0cxrDNlIuINE6rdn1JVCLMR4yPm8azo08au6urInKxvpH_ckwhhknagynEHDTxyBF_69b?key=E5dHXVUTzknfca2XYtK_swaA)**

2. Измените главу 2 в файле

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.

```

3. Закоммитьте изменения и отправьте их на GitHub:

```
git add README.md
git commit -m "Добавлен раздел о магии конфликтов"
git push origin feature-login

```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe_fd_RYkxLvGCQRV4DD8w_f74wMWCHlXE9cVCK2ShQju0HEsSj9a6IJGOH9dWQzvh15mafQm1xGFfilGXqDR_3xhBwQC3n-dgV-5A9EqS5HxOHauNOnMYdJ0fc2MtSe_xnkPxU0w?key=E5dHXVUTzknfca2XYtK_swaA)**
## 5. Разрешение конфликта

1. Вернитесь в основную ветку и попробуйте слить изменения:

```
git checkout main
git pull origin main
```
2. Возникнет конфликт. Разрешите его в файле

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

<<<<<<< HEAD
## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.
======= 
## Глава 2: Основы Git
Основные понятия и команды Git. 
>>>>>>> feature-login

```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeHkO7aLqs6R4CfCiAPvFNuNzT2pMcVewaGdHoUah0Z-QdGSRW0789wY0evJUOkQ9uCpOr5Q00MDJsUh2FU4DXLk4HmL3ml-2c6RN6HVUsMDdJwH8wxK0siKQFalLvfOhmakQz8?key=E5dHXVUTzknfca2XYtK_swaA)**
3. Разрешите конфликт, удалив метки и оставив нужные изменения:

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.
```

4. Закоммитьте разрешение конфликта и отправьте изменения на GitHub:

```
git add README.md
git commit -m "Resolved conflict in chapter 2"
git push origin main
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfJZ5legQKzS1cRiQryIpH569HmsTdGypoGCHSoMh8ZUweSFU7sCyVPIk_cdtMNKQ5ozlTGzsDtck-zlIXMH71gG2zFlh2yuq37K9V5hsk8_NT9Qqtu_CnCz4cQDejPaX4rzacD?key=E5dHXVUTzknfca2XYtK_swaA)**
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXejUu9FnjgM8VVzkJRKKDKdqQgddMhACGTCrgnzN9q14YBFXpwx-MExQDecc45_Yd7HxqbLbmLFUFWXg8AJeujk0je1prPwmxDlCtpYD69MftR5YyWU9XDL_GQE_aweyxml5isaDQ?key=E5dHXVUTzknfca2XYtK_swaA)**
