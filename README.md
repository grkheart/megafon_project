# Курсовой проект к видеокурсу от Megafon

## Задача

Построить алгоритм, который для каждой пары пользователь-услуга определит вероятность подключения услуги.

## Данные

В качестве исходных данных доступна информация об отклике абонентов на предложение подключения одной из услуг (файлы data_train.csv и data_test.csv).

Каждому пользователю может быть сделано несколько предложений в разное время, каждое из которых он может или принять, или отклонить.

Отдельным набором данных будет являться нормализованный анонимизированный набор признаков, характеризующий профиль потребления абонента (файл features.csv). Эти данные привязаны к определенному времени, поскольку профиль абонента может меняться с течением времени.

Данные train и test разбиты по периодам – на train доступно 4 месяца, а на test отложен последующий месяц.

## Итого, в качестве входных данных будут представлены:

● data_train.csv: id, vas_id, buy_time, target ● features.csv.zip: id, <feature_list>

## И тестовый набор:

● data_test.csv: id, vas_id, buy_time

target - целевая переменная, где 1 означает подключение услуги, 0 - абонент не подключил услугу соответственно. buy_time - время покупки, представлено в формате timestamp, для работы с этим столбцом понадобится функция datetime.fromtimestamp из модуля datetime. id - идентификатор абонента vas_id - подключаемая услуга

## Примечание:

Размер файла features.csv в распакованном виде весит 20 гб, для работы с ним можно воспользоваться pandas.read_csv, либо можно воспользоваться библиотекой Dask.

## Список файлов

[data_preprocessing.ipynb](https://github.com/grkheart/megafon_project/blob/main/data_preprocessing.ipynb) - предобработка данных

[model_pipeline.ipynb](https://github.com/grkheart/megafon_project/blob/main/model_pipeline.ipynb) - основная часть: обработка признаков, балансировка данных, построение пайплайнов, обучение моделей, предсказания и оценка качества моделей, выбор CatBoostClassifier в качестве основной модели для предсказания на тестовой выборке

[cat_boost_classifier_model.pickle](https://github.com/grkheart/megafon_project/blob/main/cat_boost_classifier_model.pickle) - обученная модель CatBoostClassifier в формате pickle

[answers_test.csv](https://github.com/grkheart/megafon_project/blob/main/answers_test.csv) - файл с ответами, предсказание вероятности подключения услуги по тестовой выборке

[Презентация.pdf](https://github.com/grkheart/megafon_project/blob/main/Презентация.pdf) - презентация к проекту

[Инструкция.pdf](https://github.com/grkheart/megafon_project/blob/main/Инструкция%20к%20финальному%20проекту.docx) - инструкция к выполнению проекта

## Запуск проекта

### Для запуска проекта понадобятся следующие файлы:

data_train.csv
data_test.csv
features.csv.zip
Их можно скачать [по ссылке](https://drive.google.com/drive/folders/1LCUYS7uXKKZenNn8fUTjq_iupelNRAfQ)

Файлы должны находиться в корне проекта. Архив features.csv.zip нужно распаковать.
