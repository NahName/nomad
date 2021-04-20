# nomad

Как я это вижу:

1. создаем виртуальные машины, 3 шт
2. применяем ансибл роль на всех.
3. отправляем скрипты "copy hlc" на виртуалки и исполняем их agent-ом, все это ансиблом. Должен собраться кластер Nomad-а.
4. ставим докер на виртуалки копируем файлы-задачи по использованию docker-драйвера. стартуем job.


# Environment

- Install [direnv](https://github.com/direnv/direnv/blob/master/docs/installation.md)

- Add [hook](https://github.com/direnv/direnv/blob/master/docs/hook.md)

```shell
# allow direnv
direnv allow

# install role vendors
ansible-galaxy install -r requirements.yml --force

# run playbook
ansible-playbook site.yml -i inventory
```
