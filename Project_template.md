# Project_template

Тип: Материал
Родитель: Описание проекта для 11 когорты (https://www.notion.so/11-03abbbbc8bcb49ed9b85c9b6d1174056?pvs=21)

Это шаблон для решения проектной работы. Структура этого файла повторяет структуру заданий. Заполняйте его по мере работы над решением.

# Задание 1. Анализ и планирование

<aside>
💡

«Тёплый дом» — это небольшая компания, которая организует удалённое управление отоплением в доме. Недавно она выиграла тендер и получила заказ на создание экосистемы умных посёлков на территории нескольких регионов страны.
Состояние компании в настоящий момент не позволяет в полной мере реализовать новые бизнес-цели. Для этого требуется пересмотр и оптимизация всей экосистемы.

</aside>

### 1. Описание функциональности монолитного приложения

**Управление отоплением:**

- Пользователи могут удалённо включать/выключать отопление в своих домах.
- Система поддерживает подключение только путем выезда специалиста.

**Мониторинг температуры:**

- Пользователи могут просматривать текущую температуру в своих домах через веб-интерфейс.
- Система получает данные о температуре с датчиков, установленных в домах.
- Система не поддерживает самостоятельное подключение нового датчика

### 2. Анализ архитектуры монолитного приложения

Язык программирования: Java.
База данных: PostgreSQL.
Архитектура: Монолитная, все компоненты системы (обработка запросов, бизнес-логика, работа с данными) находятся в рамках одного приложения.
Взаимодействие: Синхронное, запросы обрабатываются последовательно.
Масштабируемость: Ограничена, так как монолит сложно масштабировать по частям.
Развёртывание: Требует остановки всего приложения.

### 3. Определение доменов и границы контекстов

- Домен: Управление устройствами
    - Поддомен: Управление отоплением
        - Контекст: Включение/выключение отопления
        - Контекст: Изменение температуры
- Домен: Мониторинг состояния
    - Поддомен: Мониторинг температуры
        - Контекст: Просмотр текущей температуры через датчик

### **4. Проблемы монолитного решения**

Высокий риск ошибок. Изменения в одной части приложения могут непредсказуемо влиять на другие части. Из-за этого вырастает вероятность возникновения ошибок.
Длительные циклы разработки и развёртывания. При каждом изменении приходится тестировать всё приложение целиком. Это замедляет выпуск новых функций.
Трудно управлять командой. Изменения, которые вносит одна команда, влияют на работу других команд.
Трудно масштабировать отдельные компоненты системы.

### 5. Визуализация контекста системы — диаграмма С4

[C4 Context](/diagrams/c4/context/context.puml)

![C4 Context](/diagrams/c4/context/context.svg)

# Задание 2. Проектирование микросервисной архитектуры

**Диаграмма контейнеров (Containers)**

[C4 Container](/diagrams/c4/container/container.puml)

![C4 Container](/diagrams/c4/container/container.svg)

**Диаграммы компонентов (Components)**

[C4 Component Device Management](/diagrams/c4/component/component_device_management.puml)

![C4 Component Device Management](/diagrams/c4/component/component_device_management.svg)

[C4 Component Gate](/diagrams/c4/component/component_gate.puml)

![C4 Component Device Management](/diagrams/c4/component/component_gate.svg)

[C4 Component Heating](/diagrams/c4/component/component_heating.puml)

![C4 Component Heating](/diagrams/c4/component/component_heating.svg)

[C4 Component Lighting](/diagrams/c4/component/component_lighting.puml)

![C4 Component Lighting](/diagrams/c4/component/component_lighting.svg)

[C4 Component Rules](/diagrams/c4/component/component_rules.puml)

![C4 Component Rules](/diagrams/c4/component/component_rules.svg)

[C4 Component Surveillance](/diagrams/c4/component/component_surveillance.puml)

![C4 Component Surveillance](/diagrams/c4/component/component_surveillance.svg)

**Диаграммы кода (Code)**

[C4 CODE Device Management](/diagrams/c4/code/code_device_management.puml)

![C4 CODE Device Management](/diagrams/c4/code/code_device_management.svg)

[C4 CODE Surveillance](/diagrams/c4/code/code_surveillance.puml)

![C4 CODE Surveillance](/diagrams/c4/code/code_surveillance.svg)

[C4 Sequence Heating](/diagrams/c4/code/sequence_heating.puml)

![C4 Sequence Heating](/diagrams/c4/code/sequence_heating.svg)

# Задание 3. Разработка ER-диаграммы

[ER Diagram](/diagrams/er/er.puml)

![ER Diagram](/diagrams/er/er.svg)

# ❌  Задание 4. Создание и документирование API

### 1. Тип API

Укажите, какой тип API вы будете использовать для взаимодействия микросервисов. Объясните своё решение.

### 2. Документация API

Здесь приложите ссылки на документацию API для микросервисов, которые вы спроектировали в первой части проектной работы. Для документирования используйте Swagger/OpenAPI или AsyncAPI.