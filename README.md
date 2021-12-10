# MyMonitoring

# Установить Docker

Сначала проверяем, что у нас есть права sudo:
$ sudo -l

Установить cURL
Вам понадобится cURL , чтобы загрузить установочный скрипт.

Чтобы установить cURL в Linux , выполните следующую команду:

$ sudo apt-get update
$ sudo apt-get install curl
$ curl --version

Чтобы загрузить сценарий get-docker.sh , выполните следующие команды.

$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sh get-docker.sh

Добавить пользователя в группу докеров

Для выполнения команд докеров вам потребуются права sudo.
Однако вы можете добавлять пользователей в группу докеров, чтобы не добавлять к командам префикс sudo


Настроить репозитории Docker
Затем вам нужно будет настроить репозитории Docker и убедиться, что вы загружаете пакеты из безопасных и официальных репозиториев Docker.

Для этого установите следующие пакеты.
$ sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common


Добавить официальные ключи Docker GPG
Чтобы добавить официальные ключи Docker GPG , выполните следующую команду.

$ curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
Если команда выполнена успешно, терминал должен вернуть ОК.


Проверить отпечаток ключа
Чтобы убедиться, что вы взяли официальный и безопасный ключ Docker, вам нужно найти отпечаток пальца в вашем ключе.
Выполните следующую команду:
$ sudo apt-key fingerprint 0EBFCD88



Установите Docker CE на свой экземпляр
Чтобы получить стабильный репозиторий из Docker, вам необходимо выполнить следующую команду.

$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"

Теперь, когда вы закончили, просто установите docker-ce на свой компьютер.

$ sudo apt-get update
$ sudo apt-get install docker-ce
Это должно установить Docker как службу. Чтобы проверить это, выполните следующую команду:

$ sudo systemctl status docker

Опять же, добавьте пользователя в группу докеров, чтобы пользователь мог выполнять команды докеров без sudo.

$ sudo groupadd docker
$ sudo usermod -aG docker devconnected
$ sudo reboot
И, наконец, проверьте свою версию Docker .

$ docker -v
Docker version 19.03.1, build 74b1e89

Docker CE, с другой стороны, представляет собой архитектуру клиент-сервер, которая позволяет клиенту взаимодействовать с серверами Docker через интерфейс командной строки Docker.

Чтобы установить docker-machine , выполните следующую команду.

$ sudo - i

$ curl -L https://github.com/docker/machine/releases/download/v0.16.1/docker-machine-`uname -s`-`uname -m` >/tmp/docker-machine &&
    chmod +x /tmp/docker-machine &&
    sudo cp /tmp/docker-machine /usr/local/bin/docker-machine 

$ sudo +x /usr/local/bin/docker-machine
$ exit


Установить docker-compose в Linux
Опять же, docker-compose по умолчанию не входит в состав Docker Community Edition.

Docker-compose - это инструмент, который позволяет вам «составлять» контейнеры Docker, то есть запускать несколько контейнеров в одной изолированной среде.

Чтобы установить docker-compose, выполните следующие команды:
$ sudo - i
$ curl -L https://github.com/docker/compose/releases/download/1.24.1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
$ sudo +x /usr/local/bin/docker-compose
$ exit
