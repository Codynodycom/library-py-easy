# Возможности `turtle` в примерах

### Рисование звезды

<div>
    <img src="images/t11.png">
</div>

```python
import turtle

# Создаём черепаху
t = turtle.Turtle()
t.color("blue")    # Устанавливаем цвет линии
t.pensize(2)       # Устанавливаем толщину линии

# Рисуем звезду
for _ in range(5):
    t.forward(100)  # Черепаха движется вперёд на 100 пикселей
    t.right(144)    # Поворот направо на 144 градуса

# Завершаем работу с экраном
turtle.done()
```

### Спиральная анимация

<div>
    <img src="images/t12.png">
</div>

```python
import turtle

t = turtle.Turtle()
t.speed(0)  # Устанавливаем максимальную скорость
colors = ["red", "purple", "blue", "green", "yellow", "orange"]  # Список цветов

# Рисуем спираль
for i in range(50):
    t.color(colors[i % 6])   # Меняем цвет
    t.forward(5 * i)         # Увеличиваем длину линии
    t.right(144)             # Поворачиваем направо на 144 градуса

# Завершаем работу с экраном
turtle.done()
```

### Анимация солнечной системы

<div>
    <img src="images/t13.png">
</div>

```python
import turtle
import math

# Создаём экран и устанавливаем фон
screen = turtle.Screen()
screen.bgcolor("black")  # Цвет фона - чёрный

# Создаём солнце
sun = turtle.Turtle()
sun.shape("circle")      # Устанавливаем форму "круг"
sun.color("yellow")      # Цвет - жёлтый
sun.shapesize(3)         # Увеличиваем размер

# Создаём планету
planet = turtle.Turtle()
planet.shape("circle")
planet.color("blue")
planet.penup()           # Поднимаем "ручку", чтобы не рисовать
planet.goto(0, -100)     # Устанавливаем начальную позицию

# Вращаем планету вокруг солнца
for angle in range(360):
    x = 100 * math.cos(angle)  # Вычисляем x-координату
    y = 100 * math.sin(angle)  # Вычисляем y-координату
    planet.goto(x, y)            # Перемещаем планету в новые координаты

# Завершаем работу с экраном
turtle.done()
```

### Цветочный узор

<div>
    <img src="images/t14.png">
</div>

```python
import turtle

t = turtle.Turtle()
t.speed(0)           # Устанавливаем максимальную скорость
t.color("magenta")   # Цвет линии - малиновый

# Рисуем круги, создавая цветочный узор
for _ in range(36):
    t.circle(100)    # Рисуем круг радиусом 100 пикселей
    t.right(10)      # Поворачиваем черепаху на 10 градусов

# Завершаем работу с экраном
turtle.done()
```

### Мозаика из квадратов

<div>
    <img src="images/t15.png">
</div>

```python
import turtle

t = turtle.Turtle()
t.speed(0)          # Устанавливаем максимальную скорость
t.color("cyan")     # Цвет линии - бирюзовый

# Рисуем мозаичный узор
for _ in range(36):
    for _ in range(4):
        t.forward(100)   # Движемся вперёд на 100 пикселей
        t.right(90)      # Поворачиваем направо на 90 градусов
    t.right(10)          # Поворачиваем черепаху на 10 градусов

# Завершаем работу с экраном
turtle.done()
```

### Рисование шахматной доски

<div>
    <img src="images/t16.png">
</div>

```python
```

### Простой домик

<div>
    <img src="images/t17.png">
</div>

```python
import turtle

t = turtle.Turtle()

# Рисуем основание дома
t.color("brown")
t.begin_fill()
for _ in range(4):
    t.forward(100)
    t.right(90)
t.end_fill()

# Рисуем крышу
t.color("red")
t.begin_fill()
t.left(45)
t.forward(70)
t.right(90)
t.forward(70)
t.end_fill()

# Рисуем дверь
t.color("blue")
t.penup()
t.goto(25, -100)
t.setheading(90)
t.pendown()
t.begin_fill()
for _ in range(2):
    t.forward(40)
    t.right(90)
    t.forward(20)
    t.right(90)
t.end_fill()

# Завершаем работу с экраном
turtle.done()
```

### Часы с кругом и отметками

<div>
    <img src="images/t18.png">
</div>

```python
import turtle

t = turtle.Turtle()
t.speed(0)

# Рисуем круг для часов
t.penup()
t.goto(0, -150)
t.pendown()
t.circle(150)

# Рисуем отметки на циферблате
t.penup()
t.goto(0, 0)
t.setheading(90)

for _ in range(12):
    t.forward(130)
    t.pendown()
    t.forward(20)
    t.penup()
    t.backward(150)
    t.right(30)

# Завершаем работу с экраном
turtle.done()
```

### Спиральный цветочный узор

<div>
    <img src="images/t19.png">
</div>

```python
import turtle

t = turtle.Turtle()
t.speed(0)
colors = ["red", "orange", "yellow", "green", "blue", "purple"]

# Рисуем спиральные круги
for i in range(50):
    t.color(colors[i % 6])  # Меняем цвет на каждый круг
    t.circle(100 - i * 2)   # Рисуем круги уменьшающегося радиуса
    t.right(15)             # Поворачиваем черепаху на 15 градусов

# Завершаем работу с экраном
turtle.done()
```

### Анимация змейки

<div>
    <img src="images/t20.png">
</div>

```python
import turtle

# Создаём объект черепахи
t = turtle.Turtle()
t.shape("square")  # Задаём форму "квадрат"
t.color("green")   # Цвет - зелёный
t.speed(5)         # Скорость черепахи

# Настройка частей тела змейки
body_parts = []

# Создаём 20 частей тела
for i in range(20):
    part = turtle.Turtle()
    part.shape("square")
    part.color("green")
    part.penup()
    part.goto(-10 * i, 0)  # Размещаем части змейки по горизонтали
    body_parts.append(part)

# Движение змейки
for _ in range(100):
    for i in range(len(body_parts) - 1, 0, -1):
        x, y = body_parts[i - 1].pos()  # Получаем позицию предыдущей части
        body_parts[i].goto(x, y)        # Двигаем текущую часть на позицию предыдущей
    body_parts[0].forward(20)           # Двигаем голову змейки вперёд

# Завершаем работу с экраном
turtle.done()
```
