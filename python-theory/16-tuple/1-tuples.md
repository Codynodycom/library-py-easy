# Кортежи

**Кортеж** (tuple) — это упорядоченная неизменяемая коллекция элементов в Python. Это означает, что после создания кортежа его содержимое нельзя изменить — вы не можете добавлять, удалять или изменять элементы. Кортежи похожи на списки, но с одной ключевой разницей — они неизменяемы (immutable).

```python
# Создание кортежа
my_tuple = (1, 2, 3, 'apple', 'banana')

# Доступ к элементам через индексы
print(my_tuple[0])  # 1
print(my_tuple[3])  # 'apple'
```

### Зачем использовать кортежи?

- **Неизменяемость**: Если данные не должны меняться в процессе работы программы, кортежи обеспечивают защиту от случайных изменений. Это особенно полезно для создания константных наборов данных.

- **Быстродействие**: Кортежи занимают меньше памяти и работают быстрее, чем списки. Если вам нужны только чтение и доступ к данным, использование кортежей может повысить производительность программы.

- **Использование в качестве ключей словарей**: Кортежи могут быть использованы в качестве ключей для словарей, так как они неизменяемы (в отличие от списков).

### Основные операции с кортежами

Кортежи поддерживают большинство операций, доступных для списков, таких как доступ по индексу, срезы и циклы. Однако, так как кортежи неизменяемы, операции, связанные с изменением данных (добавление, удаление, изменение элементов), невозможны.

**Доступ к элементам по индексу**

```python
fruits = ('apple', 'banana', 'orange')
print(fruits[0])  # 'apple'
```

**Использование срезов**

```python
numbers = (1, 2, 3, 4, 5)
print(numbers[1:3])  # (2, 3)
```

**Циклы по кортежам**

```python
for fruit in fruits:
    print(fruit)
```

### Почему кортежи нужны?

- **Защита данных**: Кортежи обеспечивают защиту от непреднамеренного изменения данных, что делает их идеальными для использования в тех ситуациях, когда данные должны быть неизменными.

- **Оптимизация производительности**: Кортежи занимают меньше памяти и быстрее работают, чем списки. Это может быть важно в программах с большим количеством данных или высокими требованиями к производительности.

- **Использование в сложных структурах данных**: Кортежи часто используются для создания сложных структур данных, таких как вложенные кортежи и словари, где ключами могут быть неизменяемые типы данных.
