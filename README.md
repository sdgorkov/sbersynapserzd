# sbersynapserzd

Репозиторий для показа сберсинапса


## Доступы и контакты:


Kubernates Dashboard:
https://37.230.195.15/#/login

Kiali:
http://37.18.121.238/kiali/

Grafana:
http://37.230.195.90/d/vu8e0VWZk/istio-performance-dashboard?orgId=1&refresh=10s

Jaeger:
http://37.18.121.146/jaeger/search


в качестве средств авторизации используем токен (там где спросит):

eyJhbGciOiJSUzI1NiIsImtpZCI6IjFOVm9YVkl6ZHlXOWJjZDlzQTR4SGZWaUpuQl9Pd1BsdlJydUpPWE9RMVEifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJyemQtc2FtcGxlIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6InJ6ZC12aWV3ZXItdG9rZW4tN2pjMnMiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC5uYW1lIjoicnpkLXZpZXdlciIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50LnVpZCI6IjYzMzBjYjFmLWJhNjgtNDk3OC1iNTRkLTVmYzA5ZmI4ODcxMiIsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDpyemQtc2FtcGxlOnJ6ZC12aWV3ZXIifQ.cFQifSJX2s9Te-Olcvk1h1pk1m6HGmVkWkQs_6Ou-wD-finYi6efF9R8qf2iusa2Ec9pe3bOW5HQMBHdgdFfmIfQ8dmdQ3dqrHjhVNcfl5fP2lzuBq37i1jRS7ZP6zT_bS4nAN4Ea9hIKwg3KzWCdJI1ZKjgO2Pta-0hD32aHokee2hXzwOxpTBiJStYZqVndfAQGF19kFGnYD5ftqRHQZ3KgE-g99VzV_B9Tfj6Bu4MVwDRMm7BwmLXWXMjjOJKXV-fL1yaKYTyLYtUgKH2AubJbE0akZn_tDIYJCV5XHYTU496hSHk3aqKuaMTl2u2obZqshgM1HYLeS2z8lltcQ

Пользователь общий, смысла в личных пока нет, пока пользователи не будут что-то делать.


## SberSynapse что будем делать:

В рамках тестового показа попробуем создать уникальную точку входа, сгенерим её с помощью Symple маркета
А затем, произвести вызов сервислов из-за пределов кластера



## SberSynapse Маркет 


### Шаги:

#### Создаем конфигурацию для загрузки:
1. Логинимся в Kuber dashboard под своим SA

2. Идем по ссылке http://37.18.100.236:33333/#  ( будет ругаться на самоподписанные сертификаты - не обращайте внимания )

3. Открываем вкладку Общие компоненты выбираем там Ingress-gateway

4. Проматываем вниз специфику процесса и нажимаем "Создать"
##### заполняем параметры:
5. Называем шаблон именем своего namespace (вместе с токеном должен был быть)
6. Имя кластера любое, название проекта - ваш неймспейс, название контрольной панели  istio-system
7. Порт ингресса - любой в диапазоне, название целевого сервиса WhatToDo  порт:7788, префикс /ToDoList, протокол http

8. Нажимаем Сгенерировать (если не нажимается, вероятно что-то не заполнили)
9. Нажимаем Просмотр, разрешаем скачать файлы, если всплывет уведомление безопасности
 
#### Загружаем полученную конфигурацию:
10. В целом файл для загрузки в личный проект готов. Дальше остается соединить DevOps этап для автоматизации установки компонент, но это уже в рамках других экспериментов. Пока при необходимости можно загружать по кусочкам.
11. После загрузки конфигураций можно пробовать вызвать сервис, но для этого надо сперва загрузить сложный сервис


## SberSynapse Простой сервис и его версия:

## SberSynapse Сервис по работе с kafka:

## SberSynapse Сложный сервис:



