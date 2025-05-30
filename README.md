
# Psych Core Template

Этот репозиторий содержит шаблонную структуру базы данных для ядра психосимулятора (psych_core), разработанного как компонент MVP. База предназначена для хранения и обработки психических состояний, симптомов, методов терапии, шкал, модификаторов и их взаимосвязей, с поддержкой мультиязычия и версионирования.

## 🔧 Структура JSON

Основные разделы:

### `disorders`
Список психических расстройств.

```json
{
  "id": "depression",
  "name": {
    "ru": "Депрессия",
    "en": "Depression",
    "pl": "Depresja"
  },
  "description": {
    "ru": "Состояние сниженного настроения...",
    "en": "A state of lowered mood...",
    "pl": "Stan obniżonego nastroju..."
  },
  "symptoms": ["s1", "s2"],
  "scales": ["phq9"],
  "comorbid": ["anxiety"],
  "source": "DSM-5",
  "created_by": "system",
  "created_at": "2025-05-28"
}
```

### `symptoms`
Описание симптомов, с возможностью связей с несколькими расстройствами.

### `therapies`
Методы терапии, применимые к состояниям.

### `modifiers`
Фоновые и культурные модификаторы, влияющие на диагностику и терапию.

### `scales`
Диагностические шкалы (например, PHQ-9, GAD-7).

### `graph_edges`
Связи между сущностями для визуализации графа:

- `from` / `to`
- `type` (например, "comorbid", "masks", "requires_scale")

## 🌍 Мультиязычие

Каждая текстовая сущность содержит поля `name` и `description` с подполями `ru`, `en`, `pl`. При добавлении нового контента важно дублировать эти поля во всех языках.

## 🛠 Редактирование и масштабирование

- Все данные хранятся в едином файле `psych_core_template.json`.
- Рекомендуется использовать Retool / Appsmith / ToolJet для визуального редактирования.
- При росте базы возможен переход к GraphDB (Neo4j) или PostgreSQL.

## 🔒 Версионирование

При изменениях — коммит в Git, указание автора и даты.

## 🚀 Первое использование

1. Откройте файл `psych_core_template.json` в редакторе.
2. Изучите структуру.
3. Настройте Retool или Appsmith для формы редактирования по полям.
4. Начните наполнение.

---

**Внимание:** структура оптимизирована под MVP. При масштабировании рекомендована миграция в более специализированные СУБД и усиление схем валидации.

