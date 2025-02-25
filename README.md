# Ansible Playbook for Installing Clickhouse and Vector

## Описание

Этот Ansible playbook предназначен для установки и настройки Clickhouse и Vector на целевых хостах 

## Предварительные требования

Перед запуском playbook убедитесь, что выполнены следующие требования:

- Ansible версии 2.9 или выше установлен на контроллере.
- Управляемые узлы настроены и могут быть доступны через SSH.
- Имеется доступ к интернету для загрузки пакетов.

## Переменные

- `clickhouse_version`: Версия Clickhouse, которую следует установить.
- `clickhouse_packages`: Список пакетов Clickhouse для установки.
- `vector_version`: версия vector
- `vector_config_dir`: путь до файла конфигурации vector
- `vector_config_file`: имя файла конфигурации vector

## Инструкции по установке

1. **Склонируйте репозитарий**

2. **Подготовьте инвентори файл:**

Укажите целевые хосты, добавив их в файл инвентори, [`prod.yml`]`inventory/prod.yml`:

---
clickhouse:
  hosts:
    clickhouse-01:
      ansible_host: 
      
vector:
  hosts:
    vector-01:
      ansible_host: 


3. **Запуск playbook:**

   Выполните команду для запуска playbook:

```shell
   ansible-playbook -i inventory/prod.yml site.yml
```
   
## Роли и задачи

- **Установка Clickhouse:**
  - Скачивает необходимые пакеты.
  - Устанавливает их с помощью `apt`.
  - Создаёт базу данных.

- **Установка Vector:**
  - Скачивает необходимые пакеты.
  - Устанавливает их с помощью `apt`.
  - Через template накатывает конфиг для vector

## Обработка ошибок

В playbook предусмотрены механизмы для обработки ошибок при загрузке пакетов Clickhouse. В случае неудачи с основных зеркал, playbook пытается загрузить резервный пакет.
