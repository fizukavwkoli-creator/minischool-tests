# MiniSchool — Банк тестів

Публічний репозиторій готових тестів для платформи [MiniSchool](https://github.com/minischool-ua/minischool).

## Структура

```
index.json              ← каталог всіх тестів (MiniSchool завантажує цей файл)
tests/
  fizyka/               ← Фізика
  matematyka/           ← Математика
  istoriya/             ← Історія
```

## Формат тесту (JSON)

```json
{
  "format_version": 2,
  "title": "Назва тесту",
  "subject": "Фізика",
  "class_filter": "8",
  "time_limit": 12,
  "questions": [
    {
      "type": "single",
      "text": "Текст питання",
      "answers": [
        { "text": "Варіант А", "is_correct": 1 },
        { "text": "Варіант Б", "is_correct": 0 }
      ]
    },
    {
      "type": "multiple",
      "text": "Вибери всі правильні твердження",
      "answers": [
        { "text": "Правильне 1", "is_correct": 1 },
        { "text": "Неправильне", "is_correct": 0 },
        { "text": "Правильне 2", "is_correct": 1 }
      ]
    },
    {
      "type": "fillgap",
      "text": "Одиниця сили — ___",
      "answers": [
        { "text": "Ньютон", "is_correct": 1 },
        { "text": "Джоуль", "is_correct": 0 },
        { "text": "Ват", "is_correct": 0 }
      ]
    },
    {
      "type": "match",
      "text": "З'єднай пари:",
      "pairs": [
        { "left": "F = ma", "right": "Другий закон Ньютона" },
        { "left": "A = Fl", "right": "Механічна робота" }
      ]
    }
  ]
}
```

## Типи питань

| Тип | Опис |
|-----|------|
| `single` | Одна правильна відповідь (radio) |
| `multiple` | Кілька правильних відповідей (checkbox) |
| `fillgap` | Заповни пропуск (вибір зі списку) |
| `match` | Встанови відповідність (пари) |

## Як додати тест

1. Створи JSON файл у відповідній папці `tests/<предмет>/`
2. Додай запис до `index.json`
3. Зроби Pull Request або push до main

## Як імпортувати в MiniSchool

Адмінка → **Банк тестів** → обери тест → обери потік → **Імпортувати**
