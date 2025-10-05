# Ansible - Практические работы и эксперименты

Этот репозиторий содержит мои практические работы по изучению Ansible - инструмента для автоматизации настройки и управления инфраструктурой.

## 📚 О репозитории

Репозиторий организован по принципу **одна ветка = один проект/функционал**. Каждая ветка представляет собой законченную работу с собственной документацией, playbook'ами и примерами использования.

## 🌿 Структура веток

### Основные ветки

| Ветка | Статус | Описание |
|-------|--------|----------|
| [`main`](https://github.com/Eternity321/Ansible/tree/main) | 📘 Навигация | Главная ветка с описанием всех проектов |
| [`lemp-ansible`](https://github.com/Eternity321/Ansible/tree/lemp-ansible) | ✅ Завершено | Автоматизация развертывания LEMP стека |
| [`ansible-other-systems-stacks`](https://github.com/Eternity321/Ansible/tree/ansible-other-systems-stacks) | 🚧 В разработке | Работа с различными системами и стеками |

---

## 📂 Описание проектов

### 1️⃣ LEMP Stack Deployment
**Ветка:** [`lemp-ansible`](https://github.com/Eternity321/Ansible/tree/lemp-ansible)  
**Статус:** ✅ Завершено

Автоматизированное развертывание полноценного веб-сервера с LEMP стеком (Linux, Nginx, MySQL, PHP) с использованием Ansible и Vagrant.

**Что реализовано:**
- Автоматическая настройка виртуальных машин через Vagrant
- Установка и конфигурация Nginx
- Настройка MySQL
- Установка PHP и необходимых расширений
- Организация кода через Ansible roles

**Технологии:** Ansible, Vagrant, VirtualBox, Ubuntu, Nginx, MySQL, PHP

**Команды для запуска:**
```bash
git checkout lemp-ansible
vagrant up
cd ansible
ansible-playbook playbook.yml -i hosts.ini
```

[📖 Подробная документация в ветке](https://github.com/Eternity321/Ansible/tree/lemp-ansible)

---

### 2️⃣ Other Systems & Stacks
**Ветка:** [`ansible-other-systems-stacks`](https://github.com/Eternity321/Ansible/tree/ansible-other-systems-stacks)  
**Статус:** 🚧 В разработке

Практическая работа по автоматизации развертывания и настройки различных систем и программных стеков с помощью Ansible.

**В процессе разработки:**
- Изучение работы с различными операционными системами
- Автоматизация развертывания альтернативных веб-стеков
- Практика с различными модулями Ansible

[🔗 Перейти в ветку](https://github.com/Eternity321/Ansible/tree/ansible-other-systems-stacks)

---