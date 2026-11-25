# Лабораторная работа №6. Система контроля версий

Выполнил: студент гр. 4516 Галкин А. Д.

## Цель работы

Изучение базовых возможностей системы управления версиями, опыт работы с Git API, опыт работы с локальным и удалённым репозиторием.

## Ход работы

### 1. Fork репозитория

Репозиторий https://github.com/Kurtyanik/LR6 скопирован в личное хранилище через кнопку Fork.

<img width="1142" height="506" alt="dghfgh" src="https://github.com/user-attachments/assets/98a936e5-81b8-4825-9c3b-6778582cb681" />


### 2. Установка и настройка Git

Git установлен на компьютер. В настройках клиента указаны имя пользователя в требуемом формате и email. Личный репозиторий склонирован на компьютер.

<img width="497" height="223" alt="fghjfj" src="https://github.com/user-attachments/assets/5ad613eb-96a7-4bfa-8928-aa013a4bf1c6" />


### 3. Подтягивание изменений и история

Через веб-интерфейс GitHub в ветку master был добавлен файл text.txt. Изменения подтянуты в локальный репозиторий командой git pull. Выведена история коммитов и просмотрены последние изменения.

<img width="620" height="684" alt="fghfhfgh" src="https://github.com/user-attachments/assets/8381bbb4-a531-4e81-a9ce-7ddeb69938f8" />


### 4. Слияние с конфликтом

Была создана локальная ветка feature, в которой изменён файл text.txt. В ветке master этот же файл также был изменён. При слиянии ветки feature в master возник конфликт, который был успешно разрешён вручную. После коммита слияния побочная ветка feature удалена.

<img width="319" height="311" alt="ghjgjjgj" src="https://github.com/user-attachments/assets/5d94a9a2-69be-40fd-b92d-1be5e98bab50" />


### 5. Коммиты и откат

В файл text.txt были добавлены новые строки с отдельными коммитами. Последний коммит отменён командой git revert, которая создаёт новый коммит с обратными изменениями, сохраняя историю. Для оформления отчёта создана ветка report.

<img width="385" height="410" alt="dfgdgdg" src="https://github.com/user-attachments/assets/4f121c85-f801-4f14-b4fb-1370b285a4f2" />


### 6. Публикация отчёта

Ветка report со всеми изменениями и файлами скриншотов успешно отправлена в удалённый репозиторий на GitHub.

<img width="437" height="406" alt="fghfhfh" src="https://github.com/user-attachments/assets/53bbe0a3-d2fa-455b-b1ef-622936f9d10f" />



## Лог команд

git config --global user.name "4516 Галкин А.Д."
git config --global user.email "gad110804@gmail.com"
git clone https://github.com/articoul/LR6.git
git pull origin master
git log --all --oneline --graph
git log -p -2
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
