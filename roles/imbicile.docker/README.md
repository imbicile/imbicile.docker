## Пример Playbook

Установка docker

```yaml
- name: Install Docker
  hosts:
    - all
  become: true

  vars:
    docker_portainer: true

  roles:
    - role: imbicile.docker
      tags: docker
```

Пример контейнера

```yaml
# install rabbitmq
- name: Install rabbitmq
  community.docker.docker_container:
    name: rabbitmq
    image: rabbitmq:3.9-management
    restart_policy: always
    ports:
      - "5672:5672"
      - "15672:15672"
    env:
      RABBITMQ_DEFAULT_USER: "admin"
      RABBITMQ_DEFAULT_PASS: "password"
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

`docker_portainer` - установка portainer когда значение **true**

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
