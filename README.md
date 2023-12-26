# ACF - Генерация уникального ID для репитера

Поле [Advanced Custom Fields](https://www.advancedcustomfields.com/) будет генерировать уникальный ID. Изменить его нельзя. ID генерируется после сохранения нового репитера.

Примечание:
Хотя эта библиотека изначально была разработана для использования в повторителях, где каждому полю в блоке повторителя необходимо присвоить постоянный уникальный идентификатор, ее можно использовать везде, где требуется автоматически генерируемый уникальный идентификатор.

## :white_check_mark: Установка

```
composer require philipnewcomer/acf-unique-id-field
```

или

1. Загружаем на сайт: /inc/ACF_Field_Unique_ID.php
 
2. В файле дочерней темы functions.php вставляем:

```php
require_once get_stylesheet_directory() . '/inc/ACF_Field_Unique_ID.php';
```

3. Вызываем 'ACF_Field_Unique_ID' с помощью static method 'init()', чтобы активировать: 

```php
PhilipNewcomer\ACF_Unique_ID_Field\ACF_Field_Unique_ID::init();
```
4. Добавляем новое поле в группу и выбираем тип поля "Unique ID".

Уникальные идентификаторы будут генерироваться при первоначальном сохранении.

## :white_check_mark: Примечание

ID будет сгенерирован в следующем формате:

```
59885be6f2289
```

## :white_check_mark: Важно

При дублировании блока будут также скопированы и их ID. Это может нарушить логику работы элементов блока. Для правильной работы блоков и генерации ID необходимо вставлять новый пустой блок и не использовать дублирование.

## :white_check_mark: Использование поля с ID в шаблоне

Получение значения:

```php
$unique_id = get_sub_field( 'unique_id' );
```

Вставка/вывод значения:

```php
<?php echo esc_html( $unique_id ); ?>
```

## :white_check_mark: Как скрыть поле с ID в админке?
В поле, на вкладке Presentation - Атрибуты - Класс
вставляем значение acf-hidden

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://justgo.ink/zachest)
