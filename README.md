# Лабораторная работа №6. Система контроля версий

Выполнил: студент гр. 4516 Галкин А. Д.

## Цель работы

Изучение базовых возможностей системы управления версиями, опыт работы с Git API, опыт работы с локальным и удалённым репозиторием.

## Ход работы

### 1. Fork репозитория и клонирование

Репозиторий https://github.com/Kurtyanik/LR6 скопирован в личное хранилище через кнопку Fork. Затем личный репозиторий был склонирован на компьютер.

![Fork](screenshots/fork.png)

### 2. Установка и настройка Git

Git for Windows установлен на компьютер. В настройках клиента указаны имя пользователя в требуемом формате и email.

![Настройка git config](screenshots/config.png)

### 3. Файл через интерфейс GitHub

Через веб-интерфейс GitHub в ветку master был добавлен файл text.txt, и изменения подтянуты в локальный репозиторий командой git pull.

![Добавление файла через GitHub](screenshots/github_file.png)

![git pull](screenshots/pull.png)

### 4. История веток и последние изменения

Для просмотра истории операций и последних изменений использовались команды git log с различными флагами.

![История и изменения](screenshots/history.png)

### 5. Слияние с конфликтом

Была создана локальная ветка feature, в которой изменён файл text.txt. В ветке master этот же файл также был изменён. При слиянии ветки feature в master возник конфликт: обе ветки изменили одни и те же строки. Конфликт разрешён вручную путём редактирования файла, после чего сделан коммит слияния. Побочная ветка feature удалена.

![Конфликт при слиянии](screenshots/conflict.png)

### 6. Коммиты и откат

В файл text.txt дважды вносились изменения с отдельными коммитами. Последний коммит отменён командой git revert, которая создаёт новый коммит с обратными изменениями, сохраняя историю. Для оформления отчёта создана ветка report.

![Откат и ветка report](screenshots/revert.png)

## Лог команд

git config --global user.name "4516 Галкин А.Д."
git config --global user.email "gad110804@gmail.com"
git clone https://github.com/articoul/LR6.git
git pull origin master
git checkout -b feature
notepad text.txt
git add text.txt
git commit -m "Текст из ветки feature"
git switch master
notepad text.txt
git add text.txt
git commit -m "Изменен текст в ветке master"
git merge feature
notepad text.txt
git add text.txt
git commit -m "Разрешен конфликт слияния"
git branch -d feature
echo "Добавлена первая тестовая строка" >> text.txt
git add text.txt
git commit -m "Первое изменение файла text.txt"
echo "Добавлена вторая тестовая строка" >> text.txt
git add text.txt
git commit -m "Второе изменение файла text.txt"
git revert HEAD --no-edit
git switch -c report
mkdir screenshots
git add .
git commit -m "Добавлен отчет и скриншоты"
text


## История операций

Вывод команды `git log --pretty=format:"%h %ad %an %s" --date=short` перед финальной фиксацией:

e4e0d61 2026-11-25 4516 Галкин А.Д. Добавлен отчет и скриншоты
deee7e1 2026-11-25 4516 Галкин А.Д. Revert "Второе изменение файла text.txt"
3188326 2026-11-25 4516 Галкин А.Д. Второе изменение файла text.txt
6ab19c6 2026-11-25 4516 Галкин А.Д. Первое изменение файла text.txt
f6cac13 2026-11-25 4516 Галкин А.Д. Разрешен конфликт слияния
3ca0b88 2026-11-25 4516 Галкин А.Д. Изменен текст в ветке master
6ad898b 2026-11-25 4516 Галкин А.Д. Текст из ветки feature
a51d7e8 2026-11-25 4516 Галкин А.Д. Create text.txt
921f53b 2020-11-21 Kurtyanik Обновление информации
c08a654 2020-11-21 Kurtyanik Файл создан пустым
3c6e913 2020-11-21 Kurtyanik Initial commit
