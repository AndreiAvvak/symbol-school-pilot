# Инструкции по работе с Git для репозитория Школа-РФ

## Назначение
Этот документ содержит инструкции по работе с Git для репозитория [https://github.com/AndreiAvvak/symbol-school-pilot/](https://github.com/AndreiAvvak/symbol-school-pilot/)

## Основные команды

### 1. Проверка статуса
```bash
git --no-pager status
```

### 2. Добавление файлов в staging area
```bash
# Добавить все файлы
git add .

# Добавить конкретный файл
git add имя_файла.md
```

### 3. Создание коммита
```bash
# Простой коммит
git commit -m "Описание изменений"

# Многострочный коммит
git commit -m "Краткое описание

- Детальное описание 1
- Детальное описание 2
- Объяснение причин"
```

### 4. Отправка изменений
```bash
# Отправить в ветку main
git push origin main

# Принудительная отправка (использовать осторожно!)
git push origin main --force
```

### 5. Получение изменений
```bash
# Получить изменения с удаленного репозитория
git pull origin main
```

## Типичный рабочий процесс

### Шаг 1: Проверка текущего состояния
```bash
git --no-pager status
git --no-pager log --oneline -3
```

### Шаг 2: Добавление изменений
```bash
git add .
git --no-pager status  # Проверить что добавлено
```

### Шаг 3: Создание коммита
```bash
git commit -m "Описание изменений"
```

### Шаг 4: Отправка на сервер
```bash
git push origin main
```

### Шаг 5: Финальная проверка
```bash
git --no-pager log --oneline -3
git --no-pager status
```

## ⚠️ Важные замечания

1. **Всегда используйте `--no-pager`** для git команд в PowerShell
2. **Проверяйте статус** перед и после каждой операции
3. **Используйте информативные сообщения коммитов**
4. **Работайте только с веткой `main`** (другие ветки удалены)

## 🚨 Решение проблем

### Если push отклонен:
```bash
git pull origin main --allow-unrelated-histories
git push origin main
```

### Если нужно принудительно отправить:
```bash
git push origin main --force
```

### Если нужно откатиться к последнему коммиту:
```bash
git reset --hard HEAD
```

## Обновление из основного репозитория

Этот репозиторий синхронизируется с каталогом `pilots/school-rf` в основном репозитории `symbol-project`.

Для обновления из основного репозитория выполните следующие команды в корне `symbol-project`:

```bash
# Перейти в основной репозиторий
cd C:\symbol-project

# Обновить изменения в отдельном репозитории
git subtree push --prefix=pilots/school-rf https://github.com/AndreiAvvak/symbol-school-pilot.git main
```

## Структура репозитория

- `assets/images/badges/` - Изображения бейджей
- `бейджи/` - Описания школьных бейджей  
- `документы/` - Техническая документация школьного пилота
- `правовые-документы/` - Правовая база для внедрения в школе
- `README.md` - Основное описание проекта

## 🔗 Полезные ссылки

- [Репозиторий на GitHub](https://github.com/AndreiAvvak/symbol-school-pilot/)
- [Основной репозиторий проекта Символ](https://github.com/AndreiAvvak/symbol-project/)
- [Документация Git](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)

---

*Документ создан для команды проекта Символ*  
*Школьный пилот - внедрение системы цифровых бейджей в российской школе*
