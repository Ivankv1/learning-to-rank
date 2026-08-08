# Learning to Rank (Pointwise vs Listwise)

Проект по обучению моделей ранжирования на датасете **MQ2008** (LETOR 4.0).

## Результаты (NDCG@10)

| Подход                      | Validation | Test   |
|-----------------------------|------------|--------|
| Pointwise (LGBMRegressor)   | 0.5485     | 0.4929 |
| Listwise (LambdaRank)       | 0.5511     | 0.4907 |

## Что сделано

- Загрузка и парсинг данных в формате LETOR
- Pointwise подход (предсказание релевантности как регрессия)
- Listwise подход с использованием LightGBM LambdaRank
- Реализация корректного расчёта NDCG@10 с учётом групп запросов
- Сравнение подходов

## Основные выводы

- На датасете MQ2008 (Fold1) оба подхода показали близкое качество
- Listwise немного лучше на валидации
- Для небольших выборок Pointwise остаётся сильным и более простым baseline

## Технологии

- Python, pandas, numpy
- LightGBM (`LGBMRegressor` + `LGBMRanker`)
- scikit-learn (NDCG)
- Matplotlib, Seaborn

## Структура проекта

```text
├── notebooks/
│   └── learning_to_rank.ipynb
├── requirements.txt
└── README.md