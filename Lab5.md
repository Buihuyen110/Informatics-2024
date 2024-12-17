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


# Задачи 
1. Введение
2. Работа с ветками
3. Работа с удаленным репозиторием
4. Моделирование конфликта
5. Разрешение конфликта

# Решение
## 1. Введение
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

## 2. Работа с ветками

1. Создала новый текстовый файл с базовой структурой книги:
```
# Название книги

## Глава 1: Введение
Здесь будет введение в тему книги.

## Глава 2: Основы Git
Основные понятия и команды Git.
```
2. Создала ветку "feature-login" для разработки новой функциональности:

```
git checkout -b feature-login
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe5xkDHf_xEeWCAhCneaSEij-EHf1LDieZ6ooUOSpwsrWsDwseA0_MAqkmkuUW0ZAoAA4ip1HpaPV9Ag2DHj9Kn32l6V0HG-TEudV6UzpQroOknGp6da-G1yr0aooIP4c0wvo6K_A?key=E5dHXVUTzknfca2XYtK_swaA)**

3. Внесила изменения в файл:
```
# Название книги

## Глава 1: Введение
Здесь будет введение в тему книги.

## Глава 2: Основы Git
Основные понятия и команды Git.

## Глава 3: Вход в систему
Раздел по новой функциональности входа в систему.
```
4. Завершила изменения, закоммила их и отправила ветку на GitHub:

```
git add README.md
git commit -m "Добавлена глава 3: Вход в систему"
git push origin feature-login
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfbKYtkPvcGzsuswexs9J4aHTvRJlZcdZk_KjKe5zNYet64KPPjAt_c2wAOUXRaaoIpMbyVmn2Fp7sz5PkzUazj3sNqw8w_yP4ehwEb6EvU92g8avxn_1caFH7HiQfkRut71TtAqQ?key=E5dHXVUTzknfca2XYtK_swaA)**

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeuUaFTed73stSP0AE_LGSGsX4qrN99ot7lx9BSjsExjI64jG88oMUzZLkYhmgN91JIjHawa2gLUFa0vQrvlXgo1QbCQ1JGuHdOqFeUj3Q5i3PB5YpPsPYG8q-u6V3MGJeb-c_DYA?key=E5dHXVUTzknfca2XYtK_swaA)**

## 3. Работа с удаленным репозиторием

1. Переключилась на основную ветку (main) и внесила изменения:

```
git checkout main
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcIcSz0ODRB9yHzkPkqWngUvtyUzxyozM2pdCaWMrxeuVxiozyZY8ESMk9Ij1K9_26-n7r4pr4WSAXA9COqRMFBnF-kSJBlrTK0WitHph93lTKMzSwxYnCaxkO8k_H_zcfa5-i9Dw?key=E5dHXVUTzknfca2XYtK_swaA)**

2. Внесила изменения в основной ветке:

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git
Основные понятия и команды Git.
```
3. Закоммила изменения и отправила их на GitHub:

```
git add <filename>
git commit -m "Изменено название книги и введение"
git push origin main
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeDKfuNOCgj_dxYA-VUBmHBLadD1xEnlgNTJgT321QAeevhYRyOfHGCJKqfmmwupgsHJnmWX20mXJAMSxBvIUsmj0b7xyoIAvfHTp9ltvdZYfiAfz_hNEiwvhCl3pWc0T4LcA6PHw?key=E5dHXVUTzknfca2XYtK_swaA)**

## 4. Моделирование конфликта

1. Вернилась в ветку "feature-login" и внесила изменения в том же участке:

```
git checkout feature-login
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf7StFC8X_U-rRY46h3i1hfb3b_Yx2Yh5tW66GuQXQ1wDCVEXUk4kaULOGKVR6CYsg0cxrDNlIuINE6rdn1JVCLMR4yPm8azo08au6urInKxvpH_ckwhhknagynEHDTxyBF_69b?key=E5dHXVUTzknfca2XYtK_swaA)**

2. Изменила главу 2 в файле

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.
```

3. Закоммила изменения и отправила их на GitHub:

```
git add README.md
git commit -m "Добавлен раздел о магии конфликтов"
git push origin feature-login
```

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe_fd_RYkxLvGCQRV4DD8w_f74wMWCHlXE9cVCK2ShQju0HEsSj9a6IJGOH9dWQzvh15mafQm1xGFfilGXqDR_3xhBwQC3n-dgV-5A9EqS5HxOHauNOnMYdJ0fc2MtSe_xnkPxU0w?key=E5dHXVUTzknfca2XYtK_swaA)**

## 5. Разрешение конфликта
1. Вернилась в основную ветку и попробовала слить изменения:

```
git checkout main
git pull origin main
```
2. Возникнет конфликт. Разрешила его в файле

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

3. Разрешила конфликт, удалив метки и оставив нужные изменения:

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.
```

4. Закоммила разрешение конфликта и отправила изменения на GitHub:

```
git add README.md
git commit -m "Resolved conflict in chapter 2"
git push origin main
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfJZ5legQKzS1cRiQryIpH569HmsTdGypoGCHSoMh8ZUweSFU7sCyVPIk_cdtMNKQ5ozlTGzsDtck-zlIXMH71gG2zFlh2yuq37K9V5hsk8_NT9Qqtu_CnCz4cQDejPaX4rzacD?key=E5dHXVUTzknfca2XYtK_swaA)**

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXejUu9FnjgM8VVzkJRKKDKdqQgddMhACGTCrgnzN9q14YBFXpwx-MExQDecc45_Yd7HxqbLbmLFUFWXg8AJeujk0je1prPwmxDlCtpYD69MftR5YyWU9XDL_GQE_aweyxml5isaDQ?key=E5dHXVUTzknfca2XYtK_swaA)**

## Задание 1 - Автоматизация проверки формата файлов при коммите

1. Создала скрипт проверки:
Создала файл с именем pre-commit в папке .git/hooks, сделала скрипт исполняемым

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe3BcKyBbu5GGayzaTDj2-bExIVQi3CODsuM8-Ss46vQkJxFsF9qWLAc0pGSEPGMhoYCJJvJYRqsAEj3i_y79o7kmA2lqqXtZPeM1JwZeBmnATKqObc54EESBgCY5oLPAA7oJWD?key=E5dHXVUTzknfca2XYtK_swaA)**

3. Добавила следующий код в скрипт:
   
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe2o9bINHeHBUOeURZod1su9hg7ag2LovifS1gy7W6sCxy8kTa7r081aG_tsB9_lS8BlhM7f-oItFy7lIfVeV1v-VLN8TjGEner56QMJPg2lJWT6YrvggUQH6SO7qmmno-1pZb5TA?key=E5dHXVUTzknfca2XYtK_swaA)**

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdrwWzy186Y1KvR1VY__AZ7DDtO5cYyg5DbjK7yO9MddNNvJKRSCumIv_7zc3zkvsV1bRZssuzDri4Xnz9B6ip35W09m5sN8IY6ly2jlt970n4VGWHLWia4zGxLj51IRYcIyOIhxw?key=E5dHXVUTzknfca2XYtK_swaA)**

3. Проверила работу скрипта:
Теперь, когда попытаюсь сделать коммит, скрипт будет автоматически выполняться. Если в моем репозитории есть .txt файлы, которые пустые или не содержат текста в конце, коммит будет отменен, и увижу соответствующее сообщение.

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd4o0N7wmjQomH06dst3KBWFkPYGE82SIc4N0WwvvhgbHjHWCeAzT0PIYv7gANT7YceRSgmtJeffqb0lHRY_lWbdiH5uF22kwE1ZAUZXiHXVrS4JBKHjuke5nqMWOKgJGhJy6g4?key=E5dHXVUTzknfca2XYtK_swaA)**

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeQo8rDHD8WwVhhtC-66EQDDMdyaiHVB1AZMD7zfdlpRMCgA-I92JMvsm6T40SN21Z6ydclr3v8PrBGCj9QgUy_K7flfu5OEqwTEUB6csC_jJFDsG9s8y7Y-OosEm1DJESK1F_v_w?key=E5dHXVUTzknfca2XYtK_swaA)**

## Задание 2 - Использование Git Flow в проекте

1. В корне репозитория выполните инициализацию Git Flow.

```
git flow init
```

2. Создала ветку для новой функциональности, допустим она называется "task-management":
```
git flow feature start task-management
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfGz0UJZ_cbhZCpgfw4kv9cFk5WnrGTM4UyJEU6lfD4H8wpWy0eX9ttGvlMkBu7V-32BnI85IuLZz3Z6ORIenk5QgfWtmsI1pef6RGI-oJrNnKot3Xb699xNdx02MiN9MvqTyMd?key=E5dHXVUTzknfca2XYtK_swaA)**

4. Внесила изменения в код для добавления функционала управления задачами (в файл task_manager.py):
```
def create_task(title, description):
    # Логика создания задачи
    print(f"Создана новая задача: {title}")
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXebXXeYQik2tSfCEuQ12IablhDnBYu9YzrO0rpipwcuKZ-RJXZpo38K3a04Ruyp96RhsJiRrB3Foy5F3qExN2itvuZi60_evWmVXbjB3MUwtKyh0AsB4X6OdtxRjoZuxkCiEg60?key=E5dHXVUTzknfca2XYtK_swaA)**

Выполнила коммит изменения по мере разработки:

```
git add task_manager.py
git commit -m "Добавлен функционал управления задачами"
```

5. После завершения разработки функции завершила фичу и объедините ее с основной веткой:

```
git flow feature finish task-management
```

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdghArkyI-AKwc4jmhTrB6PTpkFvLzWLPdIcfKT7us1mHGWW4_zhhmaWh358oQSZ_EUn9ucZy8XYR2w1EE8tUaYTZrrSzEUcPN-4B5g_FFbAQdFCIlgDVoswBUQs_I7bMVrt3ICsg?key=E5dHXVUTzknfca2XYtK_swaA)**

    Git Flow автоматически переключится на ветку develop и выполнит слияние. Если есть конфликты, их нужно разрешить.

6. Переключилась на ветку "develop" и начинала создание релиза:

```
git checkout develop
git flow release start v1.0.0
```

7. Внесила изменения, связанные с релизом (обновила версию в файле version.txt):

```
echo "v1.0.0" > version.txt
git add version.txt
git commit -m "Обновлена версия для релиза v1.0.0"
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe_rb1PCEkJ0geXjcxy6TnsiUOVf7cB5AQRKSwzV1q-KGc4w-tPj_TBgepC1B3Pb_Ht83FxrCoOH3IetdVhF89YXuAyWTMb2mVs4EDeapZAknW0X7UvCkDlNtET8iQN6ZYlgbogZw?key=E5dHXVUTzknfca2XYtK_swaA)**

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXerkolILfZw0lqVbJI1b40V7iMESQLfI9TEpbKtBeOC_iuXzUtBOllh_fWiijECKKyr3mbDYk01ixvIdUFGqBnokZkTEiN-5vJ-mnEiuEfqhs7_I_u4Gj6yT1QCD3W8TJSK3Vj84Q?key=E5dHXVUTzknfca2XYtK_swaA)**
8. Завершила релиз и объединила его с ветками "develop" и "main":

```
git flow release finish v1.0.0
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfR-fmJ2Zgg5S5jMFfH1TlxBgUgu7gDH0eztoNrTbqH1HjL-MN-UR8cLM6hmxTKddVrZywNx5qhTTHNb0erZnNBSuThdB4r_1pDjTsQe6QB2zmgRtSkd-TqDG07jg6XQb4VzLQs?key=E5dHXVUTzknfca2XYtK_swaA)**

9. Создала hotfix :
```
git flow hotfix start hotfix-1.0.1
```

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeeMSqv0xUk8CFYXsN2SziQ7EiBZNlVgB_f3dP7ko-GFpnnqJ1TMr2vFpDlhwCRUQ3l6e-impf_vLznHYx_X3Q4pk2VSFGAdsCqfvTg0KRMTdyGjvTPaEBIME1mf3QgKCJ-IMYh1w?key=E5dHXVUTzknfca2XYtK_swaA)**

10. Внесила изменения для исправления ошибки и коммитила:
```
# Исправление ошибки
git add file_with_error.py
git commit -m "Исправлена критическая ошибка"
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd2_hmITpj99eX4aQovCKrCyTXc5_AchQuD7yDoYkCntuIG8y0_VL-_sfjPRuKbElnmyHv_uDGnESnpvFiUmL9YI73cvAFcMkxr1ObqgStf3t9orRNUPpf8YnSjnMzwQ7n3xpt4?key=E5dHXVUTzknfca2XYtK_swaA)**
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXesbxu_6IUCmaeNXiqC0Pv7tFEZiMBNFpVtgio5WjGtwKHONFgw4fT3VP0O7bCG2cCjsl0vFLSrCg51AVnbeSbktyMGhGN2MM3XAwKXdRwj6U7fkXw_YwZwDm9JAWqQf8FwdbLsAw?key=E5dHXVUTzknfca2XYtK_swaA)**

11. Завершила hotfix и объединила его с ветками "develop" и "main":
```
git flow hotfix finish hotfix-1.0.1
```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdgEb52NlJ1k6zxcnqFIiSxzfQkfrjtiXmKtX8vhyF_Js1dbJqcT6_ZqbAVXdD41Y29LjmmGNbWaMtvEtIomPbdNHBaZbLNKu_0ohPxZ_0ALM3TJcDfANzr3Y0Kq4HlwsDJlnOIJQ?key=E5dHXVUTzknfca2XYtK_swaA)**

12. Завершение работы и отправка изменений на удаленный репозиторий.
```
git push origin develop
git push origin main

```
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfYC2JNAy-Eqg4UbNS-Q4H6InhFZy_7SGyFYjMZD9dRfGCJOiSqTDMMJ47QjC8VGFwC6mzN4QsnsvvyoO7v0PfNz6zCFCgnDTyK98PJEI9peQLH8orMQoLwWaxMnND2ng1rg-gXNw?key=E5dHXVUTzknfca2XYtK_swaA)**
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcBdnx28p9MXOGEq34pD-qidmcZg2XgWI7YKTftJEvGdCLGRHeboLyr263pL4m9Af6alFOGuZqRe5J5s8aV5hfRZePBs8NY6f87X9rf61Xdu_zc93z7Tsv097s1kelzGBX70kASBA?key=E5dHXVUTzknfca2XYtK_swaA)**

