# Что такое Git и GitHub?

Git - это распределённая система контроля версий, которая позволяет отслеживать изменения в коде, работать в командах и управлять версиями проектов.

GitHub - это облачный сервис хостинга репозиториев Git, позволяющий делиться проектами, сотрудничать, использовать CI/CD, Issues, Pull Requests и т.д.

# Начало работы.

## 1) Настройка имени и email.
  git config --global user.name "YourName"
  
  git config --global user.email "your@email.com"

## 2) Создание локального репозитория.
  Переходим в папку с проекта:
  cd path\to\project
  git init

## 3) Подключение удаленного репозитория к локальному
  git remote add origin https://github.com/yourusername/repo-name.git 

## 4) Если уже есть удаленный репозиторий, а нужно создать локальный(подключение локального репозитория к удаленному):
  git clone https://github.com/yourusername/repo-name.git 

## 5) Отправка изменений

### 1. Добавление изменений в индекс
  Добавь все изменения
  git add .

  или конкретный файл
  git add filename.txt
  
### 2. Фиксируем изменения (commit)
  git commit -m "Описание изменений"

### 3. Отправляем на удаленный сервер (push)
  git push origin main

# Полезные команды:
git status - Показывает статус текущих изменений

git log - Просмотр истории коммитов

git diff - Показывает различия между версиями файлов

git branch - Показывает список веток

git checkout <branch> - Переключение на другую ветку

git checkout -b <new-branch> - Создание новой ветки и переход на неё

git merge <branch> - Объединяет указанную ветку с текущей

git pull origin <branch> - Получает обновления из удаленного репозитория

git stash - Сохраняет временно незакомиченные изменения

git reset - Откатывает изменения

git remote -v - Показывает подключенные удаленные репозитории

git pull --rebase - Вместо merge применяет rebase (более чистая история)

git pull --no-commit - Скачивает изменения, но не делает коммит слияния

git pull --stat - Показывает статистику изменений после мёрджа


# Полезное при работе в команде:
Базовые команды:

  git pull origin dev      - Получить последние изменения перед началом работы
  
  git add .
  
  git commit -m "Fix bug in login flow"
  
  git push origin feature/login-fix
  

Работа с ветками:

  git checkout -b feature/new-header
  
  ... пишешь код ...
  
  git add .
  
  git commit -m "Add new header design"
  
  git push origin feature/new-header
  

# Работа с конфликтами:
Конфликты возникают при слиянии веток, если были изменения в одних и тех же строках кода:

При git merge или git pull появится сообщение о конфликте

Нужно вручную выбрать, какие изменения оставить

После исправления:

  git add .
  
  git commit
  

# Возможная работа с гит:
## 1. Переключаемся на dev и обновляем
  git checkout dev
  
  git pull origin dev
  

## 2. Создаем свою ветку
git checkout -b feature/contact-form

## 3. Пишем код...

## 4. Добавляем и коммитим
  git add .
  
  git commit -m "Add contact form validation"

## 5. Пушим ветку
  git push origin feature/contact-form

Затем создаем PR на GitHub и ждем ревью.

# Обновление локальной ветки.
Команда git pull — одна из самых часто используемых в командной разработке. Она обновляет локальную ветку последними изменениями из удалённого репозитория.

Команда git pull — это комбинация двух других команд:

  git fetch — скачивает изменения с удалённого репозитория, но не применяет их.
  
  git merge — автоматически объединяет эти изменения с текущей веткой.

## Когда использовать git pull
Перед началом работы над задачей (чтобы быть в курсе изменений)

После того, как кто-то из команды обновил удалённый репозиторий

Чтобы синхронизировать локальный репозиторий с состоянием проекта

## Возможный порядок действий:
  git checkout dev        # переключаемся на основную ветку
  
  git pull origin dev     # получаем последние обновления
  
  git checkout -b feature/my-task   # создаём новую ветку для задачи
  
   ... пишем код ...
   
  git add .
  
  git commit -m "Add new feature"
  
  git push origin feature/my-task
