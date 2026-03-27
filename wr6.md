# МІНІСТЕРСТВО ОСВІТИ І НАУКИ УКРАЇНИ  
## КИЇВСЬКИЙ ФАХОВИЙ КОЛЕДЖ ЗВ’ЯЗКУ  

---

# ЗВІТ  
## про виконання work-case №6
### з дисципліни «Операційні системи»

---

**Виконала:**  
студентка групи **БІКС-33**  
**Сербіна Ярослава Вячеславівна**

---

**Перевірила:**  
**Сушанова Вікторія Сергіївна**

---

**Київ - 2026**

---

# Work-case №6
## Операційні системи

---

## 1. Встановлення та характеристика командних інтерпретаторів

Для виконання роботи було обрано додаткові командні інтерпретатори zsh та fish, окрім стандартного bash.

### 1.1 Встановлення командних інтерпретаторів

Для встановлення обраних командних інтерпретаторів було використано пакетний менеджер apt.
```bash
sudo apt update && sudo apt install zsh fish -y
```

<img width="828" height="527" alt="image" src="https://github.com/user-attachments/assets/a6f5c8ba-9ea7-4e8f-a971-cf85d04fd359" />

Рисунок 1 - Встановлення командних інтерпретаторів zsh та fish

### 1.2 Перевірка встановлення

Після встановлення було перевірено наявність встановлених командних інтерпретаторів у системі.
```bash
zsh --version
fish --version
```
<img width="431" height="136" alt="image" src="https://github.com/user-attachments/assets/948fc0c4-e606-47cb-8e37-7b3f47eda3e6" />

Рисунок 2 - Перевірка встановлених командних інтерпретаторів

### 1.3 Перегляд доступних командних інтерпретаторів

Для перегляду списку всіх доступних командних інтерпретаторів було використано наступну команду:
```bash
cat /etc/shells
```
<img width="484" height="312" alt="image" src="https://github.com/user-attachments/assets/8fe266d1-42b7-4ed6-94eb-f78b526e54df" />

Рисунок 3 - Список доступних командних інтерпретаторів

### 1.4 Визначення поточного командного інтерпретатора

Було визначено поточний командний інтерпретатор користувача.
```bash
echo $SHELL
```
<img width="393" height="78" alt="image" src="https://github.com/user-attachments/assets/5e16cc4e-cad5-44a5-9c3b-e30446d8f76a" />

Рисунок 4 - Визначення поточного командного інтерпретатора

### Коротка характеристика командних інтерпретаторів

bash - стандартний командний інтерпретатор операційної системи Linux, який забезпечує виконання команд, підтримку скриптів та адміністрування системи.

zsh - розширений командний інтерпретатор, який має покращене автодоповнення, підтримку плагінів та зручну роботу з історією команд.

fish - зручний та інтуїтивно зрозумілий командний інтерпретатор, який має кольорові підказки, автодоповнення та простий синтаксис.

## 2. Створення користувачів та їх розподіл по групах

### 2.1 Створення груп користувачів

Для організації доступу користувачів до системи було створено наступні групи:
```bash
technical_support
developers
financiers
founders
guests
```
Команди для створення груп:
```bash
sudo groupadd technical_support
sudo groupadd developers
sudo groupadd financiers
sudo groupadd founders
sudo groupadd guests
```
<img width="602" height="141" alt="image" src="https://github.com/user-attachments/assets/98338a60-0a54-4eca-811b-6e73de157d9a" />

Рисунок 5 - Створення груп користувачів

### 2.2 Створення користувачів та додавання їх до груп

Було створено 10 користувачів, які розподілені по 5 групах (по 2 користувачі в кожній).

Команда для створення користувачів:
```bash
sudo useradd -m -G група -s shell ім'я_користувача
```
Група Technical support (bash)
```bash
sudo useradd -m -G technical_support -s /bin/bash tech1
sudo useradd -m -G technical_support -s /bin/bash tech2
```
<img width="811" height="100" alt="image" src="https://github.com/user-attachments/assets/09a388ca-3657-4ade-b774-bb89b5c3a053" />

Рисунок 6 - Користувачі Technical support

Група Developers (zsh)
```bash
sudo useradd -m -G developers -s /usr/bin/zsh dev1
sudo useradd -m -G developers -s /usr/bin/zsh dev2
```
<img width="795" height="55" alt="image" src="https://github.com/user-attachments/assets/1ed3e68d-12fb-47ca-843f-aac2849ebbc4" />

Рисунок 7 - Користувачі Developers

Група Financiers (без доступу до shell)
```bash
sudo useradd -m -G financiers -s /sbin/nologin fin1
sudo useradd -m -G financiers -s /sbin/nologin fin2
```
<img width="798" height="48" alt="image" src="https://github.com/user-attachments/assets/068362e9-4274-40eb-9523-d4496376bb34" />

Рисунок 8 - Користувачі Financiers

Група Founders (fish)
```bash
sudo useradd -m -G founders -s /usr/bin/fish founder1
sudo useradd -m -G founders -s /usr/bin/fish founder2
```
<img width="806" height="46" alt="image" src="https://github.com/user-attachments/assets/1652ff09-6d77-4691-8193-a42a633a350a" />

Рисунок 9 - Користувачі Founders

Група Guests (без доступу до shell)
```bash
sudo useradd -m -G guests -s /sbin/nologin guest1
sudo useradd -m -G guests -s /sbin/nologin guest2
```
<img width="777" height="69" alt="image" src="https://github.com/user-attachments/assets/5ea795bf-ae8d-4e9c-aeab-cfd43d5fd1c7" />

Рисунок 10 - Користувачі Guests

### 2.3 Перевірка створених користувачів

Для перевірки користувачів у системі:
```bash
cat /etc/passwd
```
<img width="446" height="29" alt="image" src="https://github.com/user-attachments/assets/fb0b91eb-43d1-4c1d-8e68-12d075bc7da0" />

<img width="534" height="271" alt="image" src="https://github.com/user-attachments/assets/43fde958-fbf1-4ce1-af75-bcb3b78abc66" />

Рисунок 11 - Перевірка користувачів у системі

### 2.4 Перевірка груп користувачів

Для перевірки складу груп:
```bash
cat /etc/group
```
<img width="445" height="40" alt="image" src="https://github.com/user-attachments/assets/0fe2a936-46f4-40da-a71a-c9aa2ce948b9" />

<img width="353" height="242" alt="image" src="https://github.com/user-attachments/assets/4b8458c6-8030-4b47-8ff3-9fcfe992b249" />

Рисунок 12 - Перевірка груп користувачів

## Пояснення:
- Створено 5 груп користувачів відповідно до ролей
- 10 користувачів розподілено по групах
- Кожному користувачу призначено відповідний shell
- Для фінансистів та гостей доступ до shell заборонено через /sbin/nologin
