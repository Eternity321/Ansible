# LEMP Stack с Ansible

Автоматизированное развертывание LEMP стека (Linux, Nginx, MySQL, PHP) с использованием Ansible и Vagrant.

## Описание проекта

Этот проект демонстрирует автоматизацию развертывания веб-сервера с LEMP стеком на виртуальных машинах. Используется Vagrant для создания виртуальных машин и Ansible для их настройки и установки необходимого программного обеспечения.

## Технологии

- **Vagrant** - для создания и управления виртуальными машинами
- **VirtualBox** - провайдер виртуализации
- **Ansible** - для автоматизации настройки серверов
- **LEMP Stack**:
    - Linux (Ubuntu)
    - Nginx - веб-сервер
    - MySQL - СУБД
    - PHP - язык программирования

## Структура проекта

```
lemp-ansible/
├── Vagrantfile              # Конфигурация виртуальных машин
├── ansible/
│   ├── hosts.ini            # список хостов
│   ├── playbook.yml         # Основной playbook
│   └── roles/               # Роли Ansible
│       ├── nginx/
│       ├── mysql/
│       └── php/
└── README.md
```

## Быстрый старт

### 1. Клонирование репозитория

```bash
git clone https://github.com/Eternity321/lemp-ansible.git
cd lemp-ansible
```

### 2. Запуск виртуальных машин

```bash
vagrant up
```

### 3. Проверка статуса

```bash
vagrant status
```

### 4. Подключение к VM

```bash
# Подключение к первой машине
ssh vagrant@192.168.50.4
```

## Управление виртуальными машинами

### Основные команды Vagrant

```bash
# Запуск машин
vagrant up

# Остановка машин
vagrant suspend

# Перезагрузка машин
vagrant reload

# Удаление машин
vagrant destroy

# Проверка статуса
vagrant status
```

## Работа с Ansible

### Запуск playbook

```bash
cd ansible
ansible-playbook playbook.yml -i hosts.ini
```