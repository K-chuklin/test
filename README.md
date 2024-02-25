# Задание
1. Создайте веб-приложение, с API интерфейсом и админ-панелью.
2. Создайте базу данных используя миграции Django.
## Требования к реализации:

## Необходимо реализовать модель сети по продаже электроники.
Сеть должна представлять собой иерархическую структуру из 3 уровней:

- Завод;
- Розничная сеть;
- Индивидуальный предприниматель.
Каждое звено сети ссылается только на одного поставщика оборудования (не обязательно предыдущего по иерархии). Важно отметить, что уровень иерархии определяется не названием звена, а отношением к остальным элементам сети, т.е. завод всегда находится на 0 уровне, а если розничная сеть относится напрямую к заводу, минуя остальные звенья - её уровень - 1.

#### Каждое звено сети должно обладать следующими элементами:
- Название;
- Контакты:
1. Email;
2. Страна;
3. Город;
4. Улица;
5. Номер дома;
- Продукт:
1. Название;
2. Модель;
3. Дата выхода продукта на рынок;
- Поставщик (предыдущий по иерархии объект сети);
- Задолженность перед поставщиком в денежном выражении с точностью до копеек;
- Время создания (заполняется автоматически при создании).
#### Сделать вывод в админ-панели созданных объектов
На странице объекта сети добавить:

- ссылку на «Поставщика»;
- фильтр по названию города;
- «admin action», очищающий задолженность перед поставщиком у выбранных объектов.
#### Используя DRF, создать набор представлений:
- CRUD для модели поставщика (запретить обновление через API поля «Задолженность перед поставщиком»);

- Добавить возможность фильтрации объектов по определенной стране.

#### Настроить права доступа к API так, чтобы только активные сотрудники имели доступ к API.