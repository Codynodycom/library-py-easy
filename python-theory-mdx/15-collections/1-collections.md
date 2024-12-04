# Коллекции

**Коллекции в Python** — это специализированные структуры данных, предоставляемые модулем `collections`, который является частью стандартной библиотеки Python. Этот модуль расширяет встроенные типы данных (списки, кортежи, словари и множества) и предоставляет более сложные и эффективные структуры данных для выполнения различных задач.

Коллекции используются, когда стандартных структур данных Python недостаточно для решения специфических задач. Модуль `collections` предлагает такие структуры данных, как `deque`, `Counter`, `OrderedDict`, `defaultdict` и другие, которые оптимизированы для конкретных случаев использования.

### Основные структуры данных в модуле `collections`

1. `deque` (двусторонняя очередь)
**Deque** (double-ended queue) — это двусторонняя очередь, которая позволяет добавлять и удалять элементы с обоих концов с высокой эффективностью. Deque оптимизирован для выполнения операций добавления и удаления на концах очереди, что делает его подходящим для алгоритмов, где такие операции встречаются часто (например, реализация очередей и стеков).

```python
from collections import deque

# Создание очереди deque
queue = deque(['Alice', 'Bob', 'Charlie'])
print(queue)  # deque(['Alice', 'Bob', 'Charlie'])

# Добавление элементов
queue.append('David')  # Добавить в конец
queue.appendleft('Eve')  # Добавить в начало
print(queue)  # deque(['Eve', 'Alice', 'Bob', 'Charlie', 'David'])

# Удаление элементов
queue.pop()  # Удалить с конца
queue.popleft()  # Удалить с начала
print(queue)  # deque(['Alice', 'Bob', 'Charlie'])
```

##### Когда использовать:

- В алгоритмах, где нужно эффективно добавлять и удалять элементы с начала и конца, например, реализация стеков или очередей, задач на обработку данных в реальном времени.

- В задачах, связанных с обходом графов, например, для реализации алгоритма поиска в ширину (BFS).

2. `Counter`

**Counter** — это словарь, предназначенный для подсчета количества вхождений элементов. Он особенно полезен в задачах, где требуется частотный анализ данных, например, подсчёт слов в тексте или элементов в списке.

```python
from collections import Counter

# Подсчёт частоты элементов в списке
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]
count = Counter(numbers)
print(count)  # Counter({4: 4, 3: 3, 2: 2, 1: 1})

# Подсчёт частоты символов в строке
text = "hello world"
letter_count = Counter(text)
print(letter_count)  # Counter({'l': 3, 'o': 2, 'h': 1, 'e': 1, ' ': 1, 'w': 1, 'r': 1, 'd': 1})
```

##### Когда использовать:

- В задачах, где нужно быстро подсчитать количество повторений элементов, например, при анализе текстов, данных, логов или любых других коллекций.

- В алгоритмах поиска самых частых элементов (например, задача найти топ-N самых частых элементов).

3. `defaultdict`

**defaultdict** — это расширение стандартного словаря, которое автоматически создаёт значение для нового ключа с использованием функции по умолчанию. Это полезно, когда нужно инициализировать значение для несуществующего ключа без явной проверки.

```python
from collections import defaultdict

# Создание defaultdict с инициализацией списка для новых ключей
students_courses = defaultdict(list)

# Добавление курсов для студентов
students_courses['Alice'].append('Math')
students_courses['Bob'].append('Physics')
students_courses['Alice'].append('Physics')

print(students_courses)
# defaultdict(<class 'list'>, {'Alice': ['Math', 'Physics'], 'Bob': ['Physics']})
```

##### Когда использовать:

- В алгоритмах, где нужно работать с вложенными структурами данных, например, с вложенными словарями, списками или множествами.

- Для группировки данных по ключам, например, распределение данных по категориям, создание инвертированных индексов.

4. `OrderedDict`

**OrderedDict** — это словарь, который запоминает порядок добавления элементов. В Python 3.7+ встроенный `dict` сохраняет порядок, но `OrderedDict` предоставляет дополнительные возможности, такие как методы для перемещения элементов в начало или конец.

```python
from collections import OrderedDict

# Создание OrderedDict
ordered_dict = OrderedDict()
ordered_dict['banana'] = 3
ordered_dict['apple'] = 4
ordered_dict['orange'] = 2

# Порядок сохраняется
print(ordered_dict)  # OrderedDict([('banana', 3), ('apple', 4), ('orange', 2)])
```

##### Когда использовать:

- Когда важен порядок вставки элементов, например, при работе с кэшами (LRU-кэш), где порядок имеет значение.

- Для создания структур данных, где требуется отслеживать порядок операций.

5. `namedtuple`

**namedtuple** — это кортеж с именованными полями, который позволяет обращаться к элементам кортежа не только по индексу, но и по имени. Это делает код более читаемым и структурированным, особенно когда нужно передавать много связанных значений.

```python
from collections import namedtuple

# Создание namedtuple для представления точки
Point = namedtuple('Point', ['x', 'y'])
p = Point(10, 20)

# Доступ к элементам по имени
print(p.x, p.y)  # 10 20
```

#### Когда использовать:

- В алгоритмах, где нужно хранить связанные значения и обращаться к ним по имени, например, координаты, записи данных.

- Когда требуется упрощённая замена классов, чтобы избежать написания лишнего кода.

### Когда использовать коллекции?

Использование коллекций зависит от конкретной задачи и требований к структуре данных. Вот несколько примеров:

**Deque** лучше всего использовать в задачах, где нужно быстро добавлять и удалять элементы с обоих концов (например, при работе с очередями или стеком).

**Counter** полезен для анализа данных и поиска частоты элементов, например, подсчёта слов в тексте.

**Defaultdict** облегчает работу с вложенными структурами данных, так как автоматически инициализирует значения для новых ключей.

**OrderedDict** необходим в задачах, где важно сохранять порядок добавления элементов (например, в задачах, связанных с отслеживанием последовательности операций).

**Namedtuple** применяют, когда нужно хранить связанные значения в виде кортежа и обращаться к ним по имени, что повышает читаемость кода.


