# Оптимизация производственных процессов плавки стали при помощи машинного обучения

В работе рассмотрена задача уменьшения потребления электроэнергии на этапе обработки стали на металлургиеском комбинате. Данная задача решается при помощи построения модели машинного обучения.

**Стэк:**
python, numpy, pandas, sklearn, matplotlib, seaborn, Сatboost, Lightgbm

**Цель:** построить модель, предсказывающую конечную температуру стали со средней абсолютной ошибкой (MAE) меньше 6.8 градусов.

**Краткое описание проделанной работы**

Работа состоит их следующих этаопв:
    
1. Изучение данных.
    
   На этом этапе изучены исходные данные, построены графики, приведены наблюдения. На этом этапе изменения в датафреймы не вносились
    
    
2. Предобработка данных.
    
    Выполнены удаление, заполнение пропусков, генерация новых признаков согласно описанным на первом этапе наблюдениям
    Объединение исходных таблиц в одну по ключу (inner join). Удалены признаки с корреляцией Пирсона больше 0.9. Данные разделены на тренировочную и тестовую выборку в отношении 3:1. Данные смасштабированы, скаллер обучен на обучающих данных. 
    
    
3. Построение моделей и получение метрики на кросс-валидации, выбор лучшей модели и тестирование

    Было рассмотрено 3 модели: CatBoostRegressor, LGBMRegressor и RandomForestRegressor. Для поиска гиперпараметров использовадся GridSearchCV.
        
    Лучшая модель: CatBoostRegressor(loss_function="MAE", iterations=500, random_state=280823, depth=3, learning_rate=0.1)
        
    Метрика R2 лучшей модели равна 0.45, что означает что модель лучше константной модели
    
    Метрика MAE лучшей модели на тестовой выборке 6.13, что лучше целевого значения 
    
  4. Приведены выводы и анализ результатов.  Исследована важность признаков. 
