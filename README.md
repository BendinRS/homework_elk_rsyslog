# Домашняя работа "Сбор и анализ логов"

<details>
  <summary>Введение </summary>
   Функция системного журналирования (логирование) – это основной источник информации о работе системы и ошибках.
В системе Linux почти все действия записываются. Именно эти данные помогают разбираться в проблемах с ОС.
Логи могут храниться как локально, так и пересылаться на удаленную систему. Пересылка логов имеет следующие
плюсы:  

● Возможность централизованного сбора и анализа логов.Все логи со всех устройств прилетают в одно место. Это значительно упростит работу с логами.  

● Защита от удаления логов на локальной машине.  

● Оптимизация места на диске в локальной ОС. Логи не будут храниться в ОС, т.к. будут сразу пересылаться в систему сбора логов. Данная функция настраивается отдельно.  

В ОС Linux главным файлом локального журналирования является:  
+ Ubuntu/Debian — /var/log/syslog  
+ RHEL/CentOS — /var/log/messages  
+ Логи в ОС можно настроить.  
Например, указывать больше информации или отключить логирование конкретного компонента. Помимо логов, в Unix-системах используют аудит.  
В linux эту функцию выполняет linux audit daemon  

Linux Audit Daemon – это среда, позволяющая проводить аудит событий в системе Linux. Используя мощную систему аудита возможно отслеживать многие типы событий для мониторинга и проверки системы, например:  
доступ к файлам;  

+ изменение прав на файлы;  
+ просмотр пользователей, изменивших конкретный файл;  
+ обнаружение несанкционированных изменений;  
+ мониторинг системных вызовов и функций;  
+ обнаружение аномалий, таких как сбои;  
+ мониторинг набора команд.  
Аудит различает 4 вида доступа к файлу:  
```
r — чтение  
w — запись в файл  
x — выполнение файла  
a — изменение атрибута  
```
</details>

<details>
  <summary>Цели домашнего задания </summary>

+ Научится проектировать централизованный сбор логов.
+ Рассмотреть особенности разных платформ для сбора логов.
</details>

<details>
  <summary> Описание домашнего задания </summary>

1. В Vagrant разворачиваем 2 виртуальные машины web и log  
2. на web настраиваем nginx  
3. на log настраиваем центральный лог сервер на любой системе на выбор:  
+ journald;
+ rsyslog;
+ elk.
4. Настраиваем аудит, следящий за изменением конфигов nginx. Все критичные логи с web должны собираться и локально и удаленно.  
Все логи с nginx должны уходить на удаленный сервер (локально только критичные).  
Логи аудита должны также уходить на удаленную систему.  
Формат сдачи ДЗ - vagrant + ansible  
Дополнительное задание:  
развернуть еще машину с elk  
таким образом настроить 2 центральных лог системы elk и какую либо еще;  
в elk должны уходить только логи нжинкса;  
во вторую систему все остальное.  
</details>

