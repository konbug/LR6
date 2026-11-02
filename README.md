# LR6

Лабораторная работа №6

\# Отчет по лабораторной работе №6



\*\*Выполнил:\*\* студент группы 4517 Бугаков К.Д.

\*\*Тема:\*\* Работа с распределенной системой контроля версий Git, ветвление и разрешение конфликтов.



\## 1. Выполненные шаги и скриншоты



1\. Выполнен Fork исходного репозитория преподавателя в личный аккаунт GitHub.

!\[Создание Fork](screenshots/fork.png)



2\. Произведена локальная настройка глобальных параметров `user.name` и `user.email`, репозиторий склонирован на ПК.

3\. Создана локальная побочная ветка `dev` для симуляции командной работы.

4\. Смоделирован конфликт слияния: в файл `mergefile.txt` внесены конфликтующие изменения в ветках `master` и `dev`.

!\[Фиксация конфликта в консоли](screenshots/conflict.png)



5\. Маркеры конфликта успешно устранены вручную в текстовом редакторе.

!\[Разрешение конфликта в Блокноте](screenshots/note.png)



6\. Выполнено успешное слияние веток и зафиксирован коммит слияния.

7\. Проведен демонстрационный мягкий откат коммита с помощью команды `git reset --soft HEAD\~1`.

8\. Создана выделенная ветка `report-branch` для оформления материалов.



\## 2. Полный лог введенных команд



```bash

git config --global user.name "4517 Бугаков К.Д."

git config --global user.email "dmitre.dmitro@bk.ru"

git clone https://github.com

cd LR6

git pull origin master

git status

git branch dev

git add mergefile.txt

git commit -m "Сделал изменение в ветке master"

git checkout dev

git add mergefile.txt

git commit -m "изменение в ветке dev"

git checkout master

git merge dev

git add mergefile.txt

git commit -m "Разрешил конфликт слияния"

git branch -d dev

git reset --soft HEAD\~1

git commit -m "выполнил текстовый откат коммита"

git checkout -b report-branch

git log --pretty=format:"%h - %ad, %an : %s" --date=short

```



\## 3. История коммитов (Результат выполнения `git log`)



```text

dcce2f0 - 2026-11-02, 4517 Бугаков К.Д. : выполнил текстовый откат коммита

2bb9273 - 2026-11-02, 4517 Бугаков К.Д. : изменение в ветке masster

1365438 - 2026-11-02, konbug : Create TESTING.txt

921f53b - 2020-11-21, Kurtyanik : Обновление информации

c08a654 - 2020-11-21, Kurtyanik : файл создан пустым

3c6e913 - 2020-11-21, Kurtyanik : Initial commit

```

