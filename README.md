# association_rule_learning_retail
Association rule learning in a Retail

## Датасет 
https://www.kaggle.com/code/mathchi/association-rules-on-business-problem/notebook </br>
Датасет состоит из 7 столбцов и 315 строк. Каждая строка представляет собой транзакцию - продукты в корзине покупателя, каждый столбец - конкретный продукт.

## Постановка проблемы
Мы хотим найти устойчивые закономерности в наборах продуктов при помощи различных реализаций алгоритмов Apriori, FP-Growth и ECLAT, а также сравнить время работы этих алгоритмов и найти зависимость времени их работы от различного числа транзакций.

## Базовые понятия в ARL

Ассоциативное правило - закономерность вида  A→B , где A и B - множества продуктов в корзине.

itemset - уникальная транзакция. Внутри каждой транзакции представлен набор items

Support (поддержка) - это показатель "частотности" данного itemset во всех анализируемых транзакциях. 

Confidence (достоверность) - это показатель того, как часто наше правило срабатывает для всего датасета.

Lift (поддержка) - это отношение "зависимости" items к их "независимости". Lift показывает, насколько items зависят друг от друга.

Conviction (убедительность) - это "частотность ошибок" нашего правила.

## Результаты

1. Можно заметить, что FPGrowth для небольших и средних наборов данных работает быстрее, чем Apriori с реалиацией из mlxtend. Также скорость работы алгоритма FPGrowth не стремительно увеличивается при увеличении количества транзакций.
2. ECLAT на даном датасете работает хуже других алгоритмов. Можно заметить, что он лучше работает на маленьких и средних датасетах, и когда число транзакций становится больше 100 время работы алгоритма начинает стремительнее увеличиваться.
3. Можно заметить, что Apriori лучше работает при большем количестве транзакций.
4. Реализация Apriori из apyori работает эффективнее, чем из mlxtend.

![Diagram1](https://github.com/elziya/association_rule_learning_retail/raw/main/diagram1.png)
![Diagram2](https://github.com/elziya/association_rule_learning_retail/raw/main/diagram2.png)

### Вывод по датасету

Самым часто встречаемым правилом, которое выявили все алгоритмы, оказалось: большой набор продуктов + вино. Также большой набор продуктов + хлеб|молоко|сыр|яйца. Люди часто покупают сыр, яйца, молоко, хлеб вместе.
