# EMTypograph

Typograph by Evgeny Muravjev

Official site typograph: [http://mdash.ru/](http://mdash.ru/)

## Installation

### Composer

The preferred way to install this extension is through [Composer](http://getcomposer.org/).

Either run ```composer require altynbek07/emtypograph```

or add ```"altynbek07/emtypograph": "^0.1"``` to the require section of your ```composer.json```

## Using

#####1. Running typograph with the default settings:
```php
use altynbek07\emtypograph\EMTypograph;
 
$typograf = new EMTypograph();
$typograf->set_text("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
$result = $typograf->apply();
echo "<i>Настройки по умолчанию</i>: " . $result . "\n";
```

#####2. Manually сonfiguring rules:
```php
use altynbek07\emtypograph\EMTypograph;
 
$typograf = new EMTypograph();
$typograf->set_text("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
$typograf->setup(array(
	'Text.paragraphs' => 'off',
	'OptAlign.oa_oquote' => 'off',
	'OptAlign.oa_obracket_coma' => 'off',
));
$result = $typograf->apply();
echo "<i>Без параграфов, висячей пунктуации</i>: " . $result . "<br><br>\n";
```

#####3. Quick running typograph with default settings:
```php
use altynbek07\emtypograph\EMTypograph;
 
$result = EMTypograph::fast_apply("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
echo "<i>Быстрый запуск</i>: " . $result . "<br>\n";
```

#####4. Quick running typograph with manual settings:
```php
use altynbek07\emtypograph\EMTypograph;
 
$result = EMTypograph::fast_apply("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.",array(
	'Text.paragraphs' => 'off',
	'OptAlign.oa_oquote' => 'off',
	'OptAlign.oa_obracket_coma' => 'off',
));
echo "<i>Быстрый запуск настройками</i>: " . $result . "<br><br>\n";
```

#####5. Manually сonfiguring rules - use css classes instead of inline styles:
```php
use altynbek07\emtypograph\EMTypograph;
 
$typograf = new EMTypograph();
$typograf->set_text("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
$typograf->setup(array(
	'OptAlign.layout' => 'class',
));
$result = $typograf->apply();
echo "<i>Классы вместо инлайн стилей</i>: " . $result . "<br><br>\n";
```

## Author

[Altynbek Kazezov](https://github.com/altynbek07/), e-mail: [altinbek__97@mail.ru](mailto:altinbek__97@mail.ru)
