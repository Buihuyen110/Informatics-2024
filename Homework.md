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


## Задачи ##

  Получать текущие данные о погоде из API Open-Meteo каждый 5 минут каждый час и сохранять их в файл /var/logs/weather_report.log.

  Запрос:
- curl для вызова API.
- jq для обработки данных JSON
- Формат выходного файла weather_report.log: DATE: TEMPERATURE: <> , WINDSPEED: <>

## Ход работы ##

1. Загрузила необходимые инструменты, такие как:
   -   сurl: отправьте GET-запрос в API.
   -   jq: инструмент обработки JSON для извлечения полей из возвращаемых данных.

      `sudo apt install jq`

      `sudo apt install curl`

2. Создала файл fetch_weather.sh для получения данных из API Open-Meteo.

    `sudo /usr/local/bin/fetch_weather.sh`

    ```
    #!/bin/bash

    # Define the log file
    LOG_FILE="/var/logs/weather_report.log"

    # Fetch weather data from Open-Meteo API
    RESPONSE=$(curl -s "https://api.open-meteo.com/v1/forecast?latitude=59.956843&longitude=30.308941&current_weather=true")

    # Check if the response is valid
    if [[ -z "$RESPONSE" ]]; then
          echo "Failed to get information from API Open-Meteo" >> "$LOG_FILE"
    else
	      # Extract information
	      TEMPERATURE=$(echo "$RESPONSE" | jq '.current_weather.temperature')
	       WINDSPEED=$(echo "$RESPONSE" | jq '.current_weather.windspeed')

	# Write data with timestamp to file log
    echo "$(date '+%Y-%m-%d %H:%M:%S'): Temperature: $TEMPERATURE°C, Windspeed: $WINDSPEED km/h" >> "$LOG_FILE"
    fi
    ```
 ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf8j_um9oaMlFxKOvz_PfYU_b_AmFiRO4REaT80Txcvt9rJJel1Uy4e11yQL3_HCC7IlGhsYvP9fIc4xCrGygA4IuiHcvdquf7Q-Rn_magYg1Hk-oCs54YX_NiRERTptM7IjpPBOQ?key=5Osj0y9krXfMrlXtewssB73M)

+ URL-адрес API: используются API Open-Meteo с параметрами широта, долгота и current\_weather=true.

+ Curl: отправляет запрос GET, чтобы получить текущие данные о погоде.

+ jq: Извлекфет данные о температуре и скорости ветра из ответа JSON.

Убедиться, что файл сценария имеет разрешения на выполнение:

  `chmod +x fetch_weather.sh`

  ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc2MbK7tXhVs0Rv-ZVm0iCMoYkwTg4H704wtw3MUiNEmn4LdBCWgJ9SRwKdIlXBkR-zdEiSx92H6Z3xlIzf1nfL84XnfmCFEVP5SnGTlaVlCBSOBc0XshsbUVIwoq80t1X4VFKAXA?key=cBsw1W2irmEDMYjkzhntxmsO)

3. Открыла редактор crontab

    `crontab -e`

    Запускает скрипт каждый 5 минут каждый час с командой:

    `*/5 * * * * /usr/local/bin/fetch_weather.sh`

4.  Создала папку, содержащую файл прогноза погоды.

    `sudo mkdir -p /var/logs/`

    ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcO4DQfEf_Oi32f9iVaZ4aPujPpNntG7l37jJZEVZb_4PiaJPzvxGr97xwURmRl3i5QssD62LBxm_68RxOGBVKAReD9w9Xf-Dy68IaYiMss_AoiTHTdrs4xCQNlkbfiPS5mLsTKWg?key=cBsw1W2irmEDMYjkzhntxmsO)

5.  Проверила результаты в файле Weather_report.log.

    `cat /var/logs/weather_report.log`

    ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf0b-TbcAHwF7R0ywTjY7zA2hnz8Q1WJT5NKFNSS2Sr__BKi4araFl7gkI_ekCMVQK2VtdoDdEkcutTrxeg-uEUQl-VHpM4Dj1RId_vmxlDsGbkqc-cFrPPerHV8nUtCz3K4qUWPw?key=5Osj0y9krXfMrlXtewssB73M)

## Источники

- [Open-Meteo API](https://open-meteo.com/)
- [curl](https://docs.digitalocean.com/glossary/curl/)
- [Using curl to Interact with APIs (Linuxize)](https://linuxize.com/post/curl-rest-api/)
- [jq для обработки JSON](https://www.digitalocean.com/community/tutorials/how-to-transform-json-data-with-jq)
