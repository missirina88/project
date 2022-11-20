﻿Отток клиентов

Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. Вам предоставлены исторические данные о поведении клиентов и расторжении договоров с банком.

Постройте модель с предельно большим значением F1-меры. Чтобы сдать проект успешно, нужно довести метрику до 0.59. Проверьте F1-меру на тестовой выборке самостоятельно.

Дополнительно измеряйте AUC-ROC, сравнивайте её значение с F1-мерой.

Источник данных: https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling

В ходе работыбыли выполнены следующие этапы работы:

Предобработка данных:

В результате преобразований в нашем датасете мы имеем 10 признаков, 1 целевой признак (Exited). - удалили признаки Surname, customer\_id и row\_number, т.к. они не играют большой роли в анализе.

Дубликатов нет, пропуски устранены путем заполнения нулевыми значениями

Перевели тип данных в целочесленный в столбце Tenure

Признаки gender, geography преобразованы в бинарные методом OHE

Обучение трех моделей без учета дисбаланса

Построение кривой ошибок (ROC-кривая)

Борьба с дисбалансом методами Upsampling и Downsampling

Обучение трех моделей с учетом дисбаланса с помощью меодов:

балансировка весов классов

увеличение класса

уменьшение класса

Выбран оптимальная модель и метод учета дисбаланса - наилучшие результаты показала модель Случайный лес при методе борьбы с дисбалансом class\_weigth - При лучшем значении max\_depth=12, n\_estimators=14, мы имеем F1 меру =0,6061 на тестовой(валидной) выборке.
