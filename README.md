# Laravel Japanese Validation

[![CircleCI](https://circleci.com/gh/xzxzyzyz/laravel-japanese-validation/tree/master.svg?style=svg)](https://circleci.com/gh/xzxzyzyz/laravel-japanese-validation/tree/master)

Laravelで利用する日本のバリデーションルール

Laravel 5.5+

## Installation

```bash
composer require xzxzyzyz/laravel-japanese-validation
```

## Usage

### ひらがな

```php
use Xzxzyzyz\JapaneseValidation\Rules\Hiragana;

$request->validate(['name' => 'ひらがなのもじれつ'], ['name' => new Hiragana]); // true
```

### カタカナ

```php
use Xzxzyzyz\JapaneseValidation\Rules\Katakana;

$request->validate(['kana' => 'カタカナノモジレツ'], ['kana' => new Katakana]); // true
```

### 電話番号

```php
use Xzxzyzyz\JapaneseValidation\Rules\Phone;

$request->validate(['phone' => '00-0000-0000'], ['phone' => new Phone]); // true
$request->validate(['phone' => '0000000000'], ['phone' => new Phone]); // true
```

### 郵便番号

```php
use Xzxzyzyz\JapaneseValidation\Rules\PotalCode;

$request->validate(['zip' => '000-0000'], ['zip' => new PotalCode]); // true
$request->validate(['zip' => '0000000'], ['zip' => new PotalCode]); // true
```

### 都道府県

```php
use Xzxzyzyz\JapaneseValidation\Rules\Pref;

$request->validate(['pref' => '東京'], ['pref' => new Pref]); // true
```
