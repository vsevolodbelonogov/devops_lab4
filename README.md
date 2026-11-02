# Лабораторная работа П04: Ansible basics

**Выполнил:** Всеволод Белоногов, студент 3 курса ИКНТ ПГНИУ (sbelwork@gmail.com)

## Что сделано
1. Отключён cron из П02.
2. Создана вторая виртуальная машина (managed-node) из клона первой (WSL Ubuntu2), IP: 172.21.235.26.
3. На managed-node создан пользователь `runner` с правами sudo без пароля.
4. SSH-ключ с control-node скопирован на `runner@managed-node` (вход по ключу работает).
5. На control-node установлен Ansible.
6. Написан `playbook.yml`: установка nginx и копирование `index.html` в `/var/www/html/index.nginx-debian.html`.
7. Тестовый прогон `--check` и боевой прогон (оба успешны, failed=0).
8. Проверка через `curl http://172.21.235.26` — возвращает HTML с текстом «Hello from Ansible playbook!».

## Файлы
- `playbook.yml` — плейбук Ansible.
- `inventory.ini` — инвентарь.
- `index.html` — тестовая страница.
- `screenshots/` — скриншоты выполнения.

## Скриншоты
- `01_cron_removed.png` — cron из П02 отключён.
- `02_second_vm.png` — вторая машина и её IP.
- `05_runner_sudo.png` — `runner` с sudo без пароля.
- `06_ssh_copy_id.png` — SSH-ключ скопирован, вход работает.
- `07_ansible_version.png` — версия Ansible.
- `08_project_files.png` — файлы проекта.
- `09_check_run.png` — тестовый прогон (ok=3, changed=1).
- `10_prod_run.png` — боевой прогон.
- `11_curl_result.png` — `curl` возвращает HTML.

## Вывод
Ansible освоен: инвентарь, плейбук, модули `apt` и `copy`, тестовый и боевой прогоны.
