
# Masterskaya_2
В данном проекте я построю модель предсказания вероятности совершения покупки клиентами интернет-магазина в течение ближайших 90 дней.

## Инструкция по запуску

### Предварительные требования

- Python 3.8+
- pip
### Установка

***Шаг 1: Клонирование репозитория***
```git clone https://github.com/Gadzhy/Masterskaya_2.git
cd Masterskaya_2
```
git clone — копирует проект с GitHub на локальную машину.
cd Masterskaya_2 — переходит в папку проекта.

***Шаг 2: Установка зависимостей***
`pip install -r requirements.txt`
Устанавливает все библиотеки, необходимые для работы, которые перечислены в файле requirements.txt.

## 📊 Входные данные

### 1. apparel-purchases.csv
Данные о покупках клиентов:
- `client_id` — идентификатор клиента
- `quantity` — количество единиц товара
- `price` — цена товара
- `category_ids` — идентификаторы категорий товаров
- `date` — дата покупки
- `message_id` — идентификатор сообщения из рассылки (связь с messages)


### 2. apparel-messages.csv
Данные по маркетинговым рассылкам и событиям:
- `bulk_campaign_id` — идентификатор рассылки
- `client_id` — идентификатор клиента
- `message_id` — идентификатор сообщения
- `event` — действие с сообщением (отправлено, открыто, покупка и др.)
- `channel` — канал рассылки (email, sms, push и др.)
- `date` — дата действия
- `created_at` — дата и время события полностью


### 3. apparel-target_binary.csv
Целевая переменная для бинарной классификации:
- `client_id` — идентификатор клиента
- `target` — бинарный показатель (1 - клиент совершил покупку в целевом периоде, 0 - не совершил)


### 4. full_campaign_daily_event.csv
Агрегированные daily данные по событиям кампаний:
- `date` — дата
- `bulk_campaign_id` — идентификатор рассылки
- `count_event_*` — общее количество каждого типа события
- `nunique_event_*` — количество уникальных client_id для каждого типа события


### 5. full_campaign_daily_event_channel.csv
Агрегированные daily данные по каналам кампаний:
- `date` — дата
- `bulk_campaign_id` — идентификатор рассылки
- `count_event*_channel_*` — общее количество событий по типам и каналам
- `nunique_event_*_channel_*` — количество уникальных client_id по событиям и каналам



## Структура проекта

Masterskaya_2/
├── data/
│ ├── apparel-messages.csv # История сообщений клиентам
│ ├── apparel-purchases.csv # Данные о покупках
│ ├── apparel-target_binary.csv # Целевая переменная (отклик)
│ ├── full_campaign_daily_event.csv # Данные по кампаниям
│ └── full_campaign_daily_event_channel.csv # Данные по каналам
├── notebook
│   └── Masterskaya_2.ipynb
├── .gitignore
├── requirements.txt
└── README.md
