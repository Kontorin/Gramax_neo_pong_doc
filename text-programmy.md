---
order: 9
title: Текст программы
---

# ТЕКСТ ПРОГРАММЫ

## ГОСТ 19.401-78

**Обозначение программы:** ПК НПП 1.0.0  
**Название программы:** NEO ping-pong — двумерная игра на Pygame с минами  
**Версия:** 1.0.0  
**Дата:** 19.12.2025

---

## ЛИСТ УТВЕРЖДЕНИЯ И ТИТУЛЬНЫЙ ЛИСТ

| Параметр | Значение |
|----------|----------|
| **Наименование программы** | NEO ping-pong: 2D Pygame Game with Mines |
| **Назначение** | Образовательная двумерная игра в жанре Pong с элементами игровой механики (мины) |
| **Разработчик** | Учебный проект NeoPong |
| **Версия программы** | 1.0.0 |
| **Статус документа** | Рабочий |
| **Дата разработки** | 19.12.2025 |

---

## ИНФОРМАЦИОННАЯ ЧАСТЬ

### Назначение программы

Программа **NEO ping-pong** представляет собой интерактивную двумерную игру, реализованную на языке Python с использованием библиотеки Pygame. Игра воспроизводит классический жанр Pong с расширенной игровой механикой, включающей систему мин, которые взрываются при контакте с мячом, увеличивая скорость игрового элемента.

### Применение программы

Программа предназначена для:

- **Образовательных целей** — демонстрация принципов разработки игр на Python
- **Развлечения** — игра для двух игроков в формате Pong
- **Обучения программированию** — изучение основных концепций объектно-ориентированного программирования, обработки событий, физики столкновений

### Описание логической структуры

Программа состоит из следующих основных модулей:

#### 1. **Модуль settings.py** — Параметры конфигурации

Содержит все глобальные константы и параметры игры:

- **Экран:** разрешение 1268×850 пикселей, FPS = 120
- **Мяч:** размер 50×50 пикселей, начальная скорость 5 пикс/кадр
- **Ракетки:** ширина 20 пикселей, высота 200 пикселей, скорость 10 пикс/кадр
- **Мины:** размер 30×30 пикселей
- **Цвета и ресурсы:** изображения из папки assets/

#### 2. **Модуль game_objects.py** — Классы игровых объектов

Определяет основные классы:

**Класс Screen:**
- Инициализация экрана Pygame
- Загрузка фонового изображения
- Отрисовка мин и счёта игроков
- Управление часами игры (FPS)

**Класс Ball:**
- Инициализация мяча в центре экрана
- Отрисовка мяча и обновление его позиции
- Проверка столкновений с границами экрана
- Обработка столкновений с ракетками игроков
- Обработка столкновений с минами
- Логика сброса позиции при пересечении границ

**Класс Player:**
- Инициализация ракетки игрока с привязкой к клавишам управления
- Отрисовка ракетки
- Обработка клавиатурных событий (поднятие/опускание)
- Проверка границ движения ракетки
- Ведение счёта игрока

**Класс Mines:**
- Инициализация мины на случайной позиции в игровом поле
- Отрисовка мины

#### 3. **Модуль main.py** — Главный цикл программы

Реализует основной игровой цикл:

1. Инициализация Pygame и микшера звука
2. Создание игровых объектов (экран, мяч, ракетки)
3. Главный цикл обработки:
   - Обработка событий (нажатие клавиш, закрытие окна)
   - Проверка столкновений
   - Отрисовка всех объектов
   - Вывод на экран (двойная буферизация)
4. Корректное завершение программы

---

## ИСПОЛЬЗОВАННЫЕ ТЕХНИЧЕСКИЕ СРЕДСТВА

### Программное обеспечение

- **Python 3.x** — язык программирования
- **Pygame** — библиотека для разработки игр
- **Модуль random** — генерация случайных чисел

### Оборудование

- Персональный компьютер с поддержкой Pygame
- Дисплей с разрешением не менее 1280×900 пикселей
- Клавиатура для управления игроками

---

## ВЫЗОВ И ЗАГРУЗКА ПРОГРАММЫ

### Установка зависимостей

```bash
pip install pygame
```

### Запуск программы

```bash
python main.py
```

### Структура файлов проекта

```
neo_ping-pong/
├── main.py                 # Главный модуль с игровым циклом
├── game_objects.py        # Классы игровых объектов
├── settings.py            # Параметры конфигурации
├── assets/                # Папка с графическими ресурсами
│   ├── back_neon_1.png   # Фоновое изображение
│   ├── ball_neon_green.png # Изображение мяча
│   ├── red.png            # Изображение красной ракетки
│   ├── blue.png           # Изображение синей ракетки
│   └── mine_neon_red.png  # Изображение мины
└── README.md              # Документация проекта
```

---

## ВХОДНЫЕ И ВЫХОДНЫЕ ДАННЫЕ

### Входные данные

**Источник:** Событияклавиатуры

| Событие | Игрок | Действие |
|---------|-------|---------|
| Нажатие **W** | Красный (левый) | Движение ракетки вверх |
| Нажатие **S** | Красный (левый) | Движение ракетки вниз |
| Нажатие **↑** (стрелка вверх) | Синий (правый) | Движение ракетки вверх |
| Нажатие **↓** (стрелка вниз) | Синий (правый) | Движение ракетки вниз |
| Закрытие окна | — | Завершение программы |

### Выходные данные

**Назначение:** Визуализация состояния игры на экран

| Элемент | Описание |
|---------|----------|
| **Фоновое изображение** | Статичное неоновое изображение 1268×850 пикселей |
| **Мяч** | Круглый объект 50×50 пикселей, движущийся с переменной скоростью |
| **Ракетки** | Два прямоугольных объекта (20×200 пикселей) по сторонам экрана |
| **Мины** | Квадратные объекты (30×30 пикселей) на игровом поле |
| **Счёт игроков** | Числовые значения в верхней части экрана (шрифт 80pt) |
| **Частота обновления** | 120 кадров в секунду (FPS) |

---

## СИМВОЛИЧЕСКАЯ ЗАПИСЬ НА ИСХОДНОМ ЯЗЫКЕ

### Основные переменные и константы

```python
# Параметры экрана
WIDTH = 1268           # Ширина окна
HEIGHT = 850           # Высота окна
FPS = 120              # Количество кадров в секунду

# Параметры мяча
BALL_SIZE = 50         # Размер мяча (пиксели)
BALL_SPEED = 5         # Начальная скорость (пиксели/кадр)

# Параметры ракеток
PADDLE_WIDTH = 20      # Ширина ракетки
PADDLE_HEIGHT = 200    # Высота ракетки
PADDLE_SPEED = 10      # Скорость движения ракетки

# Параметры мин
MINES_SIZE = 30        # Размер мины
```

### Основные методы классов

#### Ball.draw(screen)
Отрисовывает мяч и обновляет его позицию:
```python
def draw(self, screen):
    screen.blit(self.img, self.rect)
    self.rect.x += self.speed_x
    self.rect.y += self.speed_y
    # Проверка столкновения с границами...
```

#### Ball.paddle_collision(player_red, player_blue)
Проверяет столкновения с ракетками и границами, изменяет скорость и счёт:
```python
if self.rect.colliderect(player_blue.rect):
    self.speed_x *= -1
    self.list_mine.append(new_mine)
```

#### Ball.mine_collision()
Обрабатывает столкновения мяча с минами, увеличивая скорость:
```python
if abs(self.speed_x) < 10:
    self.speed_x *= uniform(-1.25, -2.5)
```

#### Player.check_key(event)
Обрабатывает нажатие клавиш управления:
```python
if event.type == pygame.KEYDOWN:
    if event.key == self.key_up:
        self.speed = -PADDLE_SPEED
```

---

## ОПИСАНИЕ АЛГОРИТМА

### Общий алгоритм работы программы

```
1. ИНИЦИАЛИЗАЦИЯ
   ├─ Инициализировать Pygame
   ├─ Создать окно экрана (1268×850)
   ├─ Загрузить графические ресурсы
   ├─ Создать объекты игроков (ракетки)
   └─ Создать объект мяча

2. ГЛАВНЫЙ ИГРОВОЙ ЦИКЛ (while running)
   ├─ Установить FPS = 120
   ├─ ОБРАБОТКА СОБЫТИЙ
   │  ├─ Если нажата клавиша управления → изменить скорость ракетки
   │  └─ Если закрыто окно → выход из цикла
   │
   ├─ ОБНОВЛЕНИЕ СОСТОЯНИЯ
   │  ├─ Обновить позицию мяча
   │  ├─ Проверить столкновения мяча с границами
   │  ├─ Проверить столкновения мяча с ракетками
   │  │  └─ При столкновении: изменить скорость, создать мину, увеличить счёт
   │  ├─ Проверить столкновения мяча с минами
   │  │  └─ При столкновении: увеличить скорость, удалить мину
   │  └─ Обновить позицию ракеток
   │
   ├─ ОТРИСОВКА
   │  ├─ Отрисовать фон
   │  ├─ Отрисовать мины
   │  ├─ Отрисовать ракетки
   │  ├─ Отрисовать мяч
   │  ├─ Отрисовать счёт игроков
   │  └─ Обновить экран (двойная буферизация)

3. ЗАВЕРШЕНИЕ
   └─ Закрыть Pygame и окно приложения
```

### Алгоритм проверки столкновений

**Столкновение мяча с ракеткой:**
```
1. Если прямоугольник мяча пересекается с прямоугольником ракетки:
   a. Инвертировать горизонтальную скорость (speed_x *= -1)
   b. Случайно изменить скорость в диапазоне [0.5, 1.5]
   c. Случайно изменить вертикальную скорость
   d. Создать новую мину
   e. Добавить мину в список (list_mine)
```

**Столкновение мяча с миной:**
```
1. Для каждой мины в списке:
   a. Если прямоугольник мяча пересекается с прямоугольником мины:
      - Увеличить скорость в диапазоне [1.25, 2.5]
      - Удалить мину из списка
```

---

## РЕГИСТРАЦИЯ ИЗМЕНЕНИЙ

| Версия | Дата | Описание изменений | Автор |
|--------|------|-------------------|-------|
| 0.1.0 | 17.12.2025 | Первая версия разработки | NeoPong Team |
| 1.0.0 | 19.12.2025 | Финальная версия с полной документацией | NeoPong Team |

---

## ПРИЛОЖЕНИЕ А. ЛИСТИНГ ПРОГРАММЫ

### settings.py

```python
import pygame

# Параметры экрана
WIDTH = 1268
HEIGHT = 850
FPS = 120
BACKGROUND = pygame.image.load('assets/back_neon_1.png')
TITLE = "NEO ping-pong"

# Параметры мяча
BALL_SIZE = 50
BALL_IMG = pygame.image.load('assets/ball_neon_green.png')
BALL_SPEED = 5

# Параметры ракеток
PADDLE_WIDTH = 20
PADDLE_HEIGHT = 200
PADDLE_IMG_RED = pygame.image.load('assets/blue.png')
PADDLE_IMG_BLUE = pygame.image.load('assets/red.png')
PADDLE_SPEED = 10

red_player_rect = (0, HEIGHT//2, PADDLE_WIDTH, PADDLE_HEIGHT)
blue_player_rect = (WIDTH - PADDLE_WIDTH, HEIGHT//2, PADDLE_WIDTH, PADDLE_HEIGHT)

# Параметры мин
MINES_RED = pygame.image.load('assets/mine_neon_red.png')
MINES_SIZE = 30

# Цвета
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
BLUE = (0, 0, 255)
```

### game_objects.py

```python
from random import randint, choice, uniform
import pygame
from settings import *

class Screen:
    def __init__(self):
        self.screen = pygame.display.set_mode((WIDTH, HEIGHT))
        self.img = pygame.transform.scale(BACKGROUND, (WIDTH, HEIGHT))
        self.clock = pygame.time.Clock()
        pygame.display.set_caption(TITLE)
        self.font = pygame.font.Font(None, 80)
        
    def draw_mine(self, ball):
        for mine in ball.list_mine:
            mine.draw(self.screen)
            
    def show_score(self, blue_player, red_player):
        player1_score_surface = self.font.render(str(red_player.score), True, (44, 174, 247))
        player2_score_surface = self.font.render(str(blue_player.score), True, (191, 19, 21))
        self.screen.blit(player1_score_surface, (425, 150))
        self.screen.blit(player2_score_surface, (1020, 150))
        
class Ball:
    def __init__(self):
        self.rect = pygame.Rect(WIDTH//2, HEIGHT//2, BALL_SIZE, BALL_SIZE)
        self.img = pygame.transform.scale(BALL_IMG, (BALL_SIZE, BALL_SIZE))
        self.list_mine = []
        self.speed_x = BALL_SPEED
        self.speed_y = BALL_SPEED
        
    def draw(self, screen):
        screen.blit(self.img, self.rect)
        self.rect.x += self.speed_x
        self.rect.y += self.speed_y
        
        if self.rect.x < 0: self.speed_x *= -1
        if self.rect.x + BALL_SIZE > WIDTH: self.speed_x *= -1
        
        if self.rect.y < 218: self.speed_y *= -1
        if self.rect.y + BALL_SIZE > HEIGHT: self.speed_y *= -1
        
    def paddle_collision(self, player_red, player_blue):
        if self.rect.right >= WIDTH:
            player_blue.score += 1
            self.start_pos()
            self.list_mine = []
            
        if self.rect.left <= 0:
            player_red.score += 1
            self.start_pos()
            self.list_mine = []
            
        if self.rect.colliderect(player_blue.rect):
            self.rect.left = player_blue.rect.right + 1
            self.speed_x *= -1
            
            r = uniform(0.5, 1.5)
            if (self.speed_x < 0):
                self.speed_x = -BALL_SPEED * r
            else:
                self.speed_x = BALL_SPEED * r
        
            self.speed_y *= uniform(0.5, 1.5)
            new_mine = Mines(MINES_RED)
            self.list_mine.append(new_mine)
            
        if self.rect.colliderect(player_red.rect):
            self.rect.right = player_red.rect.left - 1
            self.speed_x *= -1
            
            r = uniform(0.5, 1.5)
            if (self.speed_x < 0):
                self.speed_x = -BALL_SPEED * r
            else:
                self.speed_x = BALL_SPEED * r
        
            self.speed_y *= uniform(0.5, 1.5)
            new_mine = Mines(MINES_RED)
            self.list_mine.append(new_mine)
    
    def start_pos(self):
        self.rect.center = (WIDTH//2, HEIGHT//2)
        self.speed_x = choice([-1, 1]) * BALL_SPEED
        self.speed_y = choice([-1, 1]) * BALL_SPEED
        
    def mine_collision(self):
        for mine in self.list_mine:
            if self.rect.colliderect(mine.rect):
                if abs(self.speed_x) < 10:
                    self.speed_x *= uniform(-1.25, -2.5)
                else:
                    self.speed_x *= -1
                
                if abs(self.speed_y) < 10:
                    self.speed_y *= uniform(1.25, 2.5)
                self.list_mine.remove(mine)

class Player:
    def __init__(self, data, img, key_up, key_down, color_player):
        self.rect = pygame.Rect(data)
        self.img = pygame.transform.scale(img, (PADDLE_WIDTH, PADDLE_HEIGHT))
        self.key_up = key_up
        self.key_down = key_down
        self.speed = 0
        self.score = 0
        self.color = color_player
        
    def draw(self, screen):
        screen.blit(self.img, self.rect)
        self.rect.y += self.speed
        
        if self.rect.top < 218: self.rect.top = 218
        if self.rect.bottom > HEIGHT: self.rect.bottom = HEIGHT
        
    def check_key(self, event):
        if event.type == pygame.KEYDOWN:
            if event.key == self.key_up:
                self.speed = -PADDLE_SPEED
            if event.key == self.key_down:
                self.speed = PADDLE_SPEED
                
        if event.type == pygame.KEYUP:
            if (event.key == self.key_up) or (event.key == self.key_down):
                self.speed = 0

                
class Mines:
    def __init__(self, img):
        self.rect = pygame.Rect(randint(400, WIDTH - 400),
                                randint(MINES_SIZE*2 + 218, HEIGHT - MINES_SIZE*3),
                                MINES_SIZE, MINES_SIZE)
        self.img = pygame.transform.scale(img, (MINES_SIZE, MINES_SIZE))
        
    def draw(self, screen):
        screen.blit(self.img, self.rect)
```

### main.py

```python
import pygame
from settings import *
from game_objects import *

pygame.init()
pygame.mixer.init()

game_screen = Screen()
ball = Ball()
red_player = Player(red_player_rect, PADDLE_IMG_RED, pygame.K_w, pygame.K_s, 'red')
blue_player = Player(blue_player_rect, PADDLE_IMG_BLUE, pygame.K_UP, pygame.K_DOWN, 'blue')

# Цикл игры
running = True
while running:
    game_screen.clock.tick(FPS)
    game_screen.screen.blit(game_screen.img, (0, 0))
    
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
            
        blue_player.check_key(event)
        red_player.check_key(event)
    
    ball.paddle_collision(blue_player, red_player)
    ball.mine_collision()
    game_screen.draw_mine(ball)
    
    blue_player.draw(game_screen.screen)
    red_player.draw(game_screen.screen)
    
    ball.draw(game_screen.screen)
    game_screen.show_score(blue_player, red_player)
    
    pygame.display.flip()

pygame.quit()
```

---

## ПРИЛОЖЕНИЕ Б. НОРМАТИВНЫЕ ССЫЛКИ

- ГОСТ 19.401-78 — Текст программы
- ГОСТ 19.104-78 — Основные надписи
- ГОСТ 19.105-78 — Общие требования к программным документам
- ГОСТ 19.401-78 — Текст программы. Требования к содержанию и оформлению
- Документация Pygame (https://www.pygame.org/docs/)
- Python 3 Official Documentation (https://docs.python.org/3/)

---

## ЗАКЛЮЧЕНИЕ

Документ "Текст программы" содержит полное описание структуры, логики и реализации игры NEO ping-pong согласно ГОСТ 19.401-78. Программа демонстрирует применение объектно-ориентированного программирования, обработки событий клавиатуры, физики столкновений и визуализации в 2D-приложении.

**Статус документа:** Утвержден  
**Дата утверждения:** 19.12.2025