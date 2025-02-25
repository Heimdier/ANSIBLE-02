Подготовил inventory-файл  https://github.com/Heimdier/ANSIBLE-02/blob/main/playbook/inventory/prod.yml

дописал play, который устанавливает и настраивает vector    https://github.com/Heimdier/ANSIBLE-02/blob/main/playbook/site.yml

для настройки vector добавил template vector.toml.j2 со стандартным конфигом  https://github.com/Heimdier/ANSIBLE-02/blob/main/playbook/template/vector.toml.j2

Запустил линтер ansible-lint, получил горы ошибок    

![image](https://github.com/user-attachments/assets/4aa2fe9d-8dda-4898-8e8c-691874366d25)

все поправил    

![image](https://github.com/user-attachments/assets/d1459527-1958-43d0-b533-1b07560e59b3)



Запустил плэйбук site.yml - clickhouse установился успешно   

![image](https://github.com/user-attachments/assets/786c33a2-fd75-4f28-b2ae-0517ace22260)

![image](https://github.com/user-attachments/assets/83a84cc1-9c76-4985-8ce0-d36ef7bed8ed)






