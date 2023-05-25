# Module: конструктор
```js
Module(String name, Boolean toggleable, Boolean bindable, String category);
```

# Module: методы
## `Module module.getName();`
**Описание:** даёт название модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `String moduleName`

**Пример:**
```js
var module = new Module("АвтоКопание", true, true, ModuleCategory.PLAYER);

module.getName(); // "АвтоКопание"
```
</details>

## `Module module.isToggleable();`
**Описание:** показывает, возможно ли включить модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `Boolean isToggleable`

**Примеры:**
```js
var module = new Module("Бур", true, true, ModuleCategory.PLAYER);

module.isToggleable(); // true
```

```js
var module = new Module("Суицид", false, true, ModuleCategory.PLAYER);

module.isToggleable(); // false
```
</details>

## `Module module.isBindable();`
**Описание:** показывает, возможно ли забиндить модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `Boolean isBindable`

**Примеры:**
```js
var module = new Module("АдминЧекер", true, true, ModuleCategory.MISC);

module.isBindable(); // true
```
```js
var module = new Module("UI-картинка", true, false, ModuleCategory.OTHER);

module.isBindable(); // false
```
</details>

## `Module module.getCategory();`
**Описание:** даёт название категории модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `String categoryName` (да-да, я не знаю, почему он не возвращает константный класс ModuleCategory) 

**Пример:**
```js
var module = new Module("ЕСП", true, true, ModuleCategory.MISC);

module.getCategory(); // "Misc"
```
</details>

## `Module module.isActive();`
**Описание:** показывает, активен ли модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `Boolean isActive`

**Пример:** нет
</details>

## `Module module.isBindActive();`
**Описание:** показывает, активен ли бинд модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `Boolean isBindActive`

**Пример:** нет
</details>

## `Module module.hasSettings();`
**Описание:** показывает, можно ли настроить модуль (имеет ли он настройки)
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `Boolean hasSettings`

**Пример:**
```js
var module = new Module("АвтоБан", false, true, ModuleCategory.PLAYER);

module.hasSettings(); // false

var setting = new ButtonSetting("Запуск", function(view) {
    // Ещё не сделано ¯\_(ツ)_/¯
})
module.addSetting(setting);

module.hasSettings(); // true
```
</details>
