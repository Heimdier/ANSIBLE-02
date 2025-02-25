Подготовил inventory-файл  https://github.com/Heimdier/ANSIBLE-02/blob/main/playbook/inventory/prod.yml

дописал play, который устанавливает и настраивает vector    https://github.com/Heimdier/ANSIBLE-02/blob/main/playbook/site.yml

для настройки vector добавил template vector.toml.j2 со стандартным конфигом  https://github.com/Heimdier/ANSIBLE-02/blob/main/playbook/template/vector.toml.j2

Запустил линтер ansible-lint, получил горы ошибок    

![image](https://github.com/user-attachments/assets/4aa2fe9d-8dda-4898-8e8c-691874366d25)

все поправил    

![image](https://github.com/user-attachments/assets/d1459527-1958-43d0-b533-1b07560e59b3)

Запустил плэйбук site.yml с флагом --check    получил ошибку, так как нет скачанных пакетов clickhouse

![image](https://github.com/user-attachments/assets/7745b721-65cc-487b-bfb6-de31d8147f76)

запустил плэйбук с флагом --diff    

![image](https://github.com/user-attachments/assets/33b7daff-f650-406f-a51a-bba9e38c304d)
![image](https://github.com/user-attachments/assets/872111f8-88db-40f1-a727-303896891c31)

Повторно запустил playbook с флагом --diff убедился что playbook идемпотентен

![image](https://github.com/user-attachments/assets/a7ee29cb-c3c2-42bb-819d-9d7339f34137)

Заходим на хост, проверяем:    

![image](https://github.com/user-attachments/assets/289bdd37-333c-4a99-ad5c-94c1e5da7dee)

Все ок!








