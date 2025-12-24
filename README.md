# Действия

Установка последней версии [docker](https://docs.docker.com/compose/install/) из репозитария

Так же дополнительно устанавливаетя контейнер управления [Portainer](https://docs.portainer.io/v/ce-2.11/start/install/server/docker/linux)

Ссылка на Portainer стандартная https://host_ip:9443

## Роль проверялась на дистрибутиве

```
Description: Ubuntu 20.04.2 LTS
Release: 20.04
Codename: focal
```

## Переменные

Файл переменных `roles/imbicile.docker/defaults/main.yml`

## inventory

В файле инвентаря задаются адреса хостов `ip:port` где необходимо развернуть роль [ansible](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)

## Подготовка

Ставим необходимые пакеты и свежую версию ansible. Так же добавляется в окружение путь `~/.local/bin`

```bash
sudo apt update && sudo apt install git python3-pip -y
git clone https://github.com/imbicile/imbicile.docker.git
cd imbicile.docker
pip3 install -r requirements.txt
PATH="$HOME/.local/bin:$PATH"
```

## Использование

Для установки на локальных хост

```bash
ansible-playbook playbooks/docker_local.yml
```

Для установки на хост в сети

```bash
 ansible-playbook playbooks/docker_hosts.yml
```

ansible-pull

```bash
sudo apt install ansible -y
ansible-pull -U https://github.com/imbicile/imbicile.docker.git
```
