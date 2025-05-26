## Пример Playbook

Установка docker

```yml
- hosts: docker_servers
  become: true
  roles:
    - { role: imbicile.docker, tags: docker }
```

## Переменные

`bip` - адрес контейнеров, при наложении сетей может произойти конфликт и пропадёт сеть. Поэтому разворачивается сначала конфигурация

`registry-mirrors` - адреса зеркал для использования в РФ

```yaml
docker_config:
  bip: "192.168.211.1/24"
  registry-mirrors:
    - "https://cr.yandex/mirror"
    - "https://dh-mirror.gitverse.ru"
    - "https://dockerhub.timeweb.cloud"
```

### Список зеркал

- https://cr.yandex/mirror - Яндекс
- https://dh-mirror.gitverse.ru - GitVerse
- https://dockerhub.timeweb.cloud - Timeweb
- https://mirror.gcr.io - Google
- https://c.163.com - Китай
- https://daocloud.io - Китай
- https://quay.io - Redhat
- https://registry.access.redhat.com - Redhat
- https://registry.redhat.io - Redhat
- https://public.ecr.aws - Amazon

## Статья

[https://imbicile.pp.ru/ansible-docker/](https://imbicile.pp.ru/ansible-docker/)

## Автор

[https://imbicile.pp.ru/informatsiya/](https://imbicile.pp.ru/informatsiya/)
