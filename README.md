# Домашнее задание к занятию "Резервное копирование" - "Подус Сергей"       
    
### Задание 1
Составьте команду rsync, которая позволяет создавать зеркальную копию домашней директории пользователя в директорию /tmp/backup
Необходимо исключить из синхронизации все директории, начинающиеся с точки (скрытые)
Необходимо сделать так, чтобы rsync подсчитывал хэш-суммы для всех файлов, даже если их время модификации и размер идентичны в источнике и приемнике.
На проверку направить скриншот с командой и результатом ее выполнения

Ответ:
rsync -av --delete --exclude '.*' /home/test/ /tmp/backup
![Скриншот 1](https://github.com/Wanderwille/scrinshot/blob/main/rsync.png)

### Задание 2
Написать скрипт и настроить задачу на регулярное резервное копирование домашней директории пользователя с помощью rsync и cron.
Резервная копия должна быть полностью зеркальной
Резервная копия должна создаваться раз в день, в системном логе должна появляться запись об успешном или неуспешном выполнении операции
Резервная копия размещается локально, в директории /tmp/backup
На проверку направить файл crontab и скриншот с результатом работы утилиты.

Ответ:
#!/bin/sh
rsync -av --delete --exclude '.*' /home/chistov/ /tmp/backup >> /var/log/crontab.log
![Скриншот 2](https://github.com/Wanderwille/scrinshot/blob/main/crontab%20-e.png)
![Скриншот 3](https://github.com/Wanderwille/scrinshot/blob/main/cскрипт.png)
![Скриншот 4](https://github.com/Wanderwille/scrinshot/blob/main/rsync%202.png)





