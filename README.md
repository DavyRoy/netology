# Ответы на задания

1. Перейдите в каталог src. Скачайте все необходимые зависимости, использованные в проекте.
Изучите файл .gitignore. В каком terraform-файле, согласно этому .gitignore, допустимо сохранить личную, секретную информацию?(логины,пароли,ключи,токены итд)
Выполните код проекта. Найдите в state-файле секретное содержимое созданного ресурса random_password, пришлите в качестве ответа конкретный ключ и его значение.
Раскомментируйте блок кода, примерно расположенный на строчках 29–42 файла main.tf. Выполните команду terraform validate. Объясните, в чём заключаются намеренно допущенные ошибки. Исправьте их.
Выполните код. В качестве ответа приложите: исправленный фрагмент кода и вывод команды docker ps.
Замените имя docker-контейнера в блоке кода на hello_world. Не перепутайте имя контейнера и имя образа. Мы всё ещё продолжаем использовать name = "nginx:latest". Выполните команду terraform apply -auto-approve. Объясните своими словами, в чём может быть опасность применения ключа -auto-approve. Догадайтесь или нагуглите зачем может пригодиться данный ключ? В качестве ответа дополнительно приложите вывод команды docker ps.
Уничтожьте созданные ресурсы с помощью terraform. Убедитесь, что все ресурсы удалены. Приложите содержимое файла terraform.tfstate.
Объясните, почему при этом не был удалён docker-образ nginx:latest. Ответ ОБЯЗАТЕЛЬНО НАЙДИТЕ В ПРЕДОСТАВЛЕННОМ КОДЕ, а затем ОБЯЗАТЕЛЬНО ПОДКРЕПИТЕ строчкой из документации terraform провайдера docker. (ищите в классификаторе resource docker_image )
   - Ответ: - [1](https://github.com/DavyRoy/netology/blob/main/Снимок%20экрана%20от%202024-11-14%2011-28-16.png)
   - [2](https://github.com/DavyRoy/netology/blob/main/Снимок%20экрана%20от%202024-11-14%2011-29-06.png)
   - [3](https://github.com/DavyRoy/netology/blob/main/Снимок%20экрана%20от%202024-11-14%2011-39-32.png)
1 ответ - .gitignore указывает, что файл personal.auto.tfvars не исключен и, соответственно, может быть использован для хранения конфиденциальных данных, таких как пароли и ключи.
Файлы с таким расширением обычно автоматически загружаются Terraform для определения переменных, и их можно использовать для безопасного хранения секретов, если доступ к репозиторию ограничен.
2 ответ - "v01WvS9lRdeoYndv"
3 ответ - Код содержит намеренные ошибки, которые могут включать неправильное написание имен ресурсов, такие как random_password.random_string_FAKE.resulT.
4 ответ - Ключ -auto-approve применяется, чтобы пропустить шаг подтверждения при выполнении terraform apply, что может привести к непреднамеренным изменениям ресурсов без согласования.
5 ответ - Согласно документации Terraform для провайдера Docker, параметр keep_locally предотвращает удаление образа из локальной среды, даже если сам ресурс Docker был уничтожён. Строка из документации:

keep_locally (Optional) - "If set to true, the image will not be removed from the local image store when the resource is destroyed. Defaults to false."

