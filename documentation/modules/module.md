# Модуль: конструктор
```js
Module(String name, Boolean toggleable, Boolean bindable, String category);
```

# Модуль: методы
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
});
module.addSetting(setting);

module.hasSettings(); // true
```
</details>

## `Module module.getSetting(String settingName);`
**Описание:** даёт настройку модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| -------- | -------- |
| String settingName | Название настройки |

**Возвращает:** `(Mode, Button, Slider, State, TextField)Setting setting`

**Пример:**
```js
var module = new Module("Буллинг при убийстве", false, true, ModuleCategory.PLAYER);

module.getSetting("Шутить про мамку"); // RuntimeException, потому что нету НИКАКИХ настроек

var setting = new StateSetting("Шутить про мамку", true);
module.addSetting(setting);

module.getSetting("Шутить про мамку"); // true
module.getSetting("Шутить про мамку админа"); // false
```
</details>

## `Module module.getSettings();`
**Описание:** даёт настройки модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** `(Mode, Button, Slider, State, TextField)Setting[] settings`

**Пример:**
```js
var module = new Module("Буллинг при убийстве", false, true, ModuleCategory.PLAYER);

module.getSettings(); // []

var setting = new StateSetting("Шутить про мамку", true);
module.addSetting(setting);

module.getSettings(); // [StateSetting("Шутить про мамку", true)]
```
</details>

## `Module module.addSetting(Setting setting);`
**Описание:** добавляет настройку модулю
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| (Mode, Button, Slider, State, TextField)Setting setting | Объект настройки |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("Обводка игроков", true, true, ModuleCategory.PLAYER);
var setting = new SliderSetting("Прозрачность", [250, 0, 255, 1]);

module.addSetting(setting);
```
</details>

## `Module module.addSettings(Setting[] settings);`
**Описание:** добавляет настройки модулю
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| (Mode, Button, Slider, State, TextField)Setting setting | Массив настроек |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("Обводка игроков", true, true, ModuleCategory.PLAYER);
var setting1 = new SliderSetting("Прозрачность", [250, 0, 255, 1]);
var setting2 = new SliderSetting("Яркость", [250, 0, 255, 1]);

module.addSetting(setting);
```
</details>

## `Module module.setOnToggleListener(Function callback);`
**Описание:** определяет действия при включении/выключении модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| Function(View view, boolean isActive) callback | Вызываемая функция |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("Взлом сурсов Variable", true, true, ModuleCategory.OTHER);

module.setOnToggleListener(function(view, isActive) {
    if (isActive) {
        Memory.getSymbol(1);
    }
}); // Функция будет вызвана, когда модуль будет включён
```
</details>

## `Module module.setOnClickListener(Function callback);`
**Описание:** определяет действия при нажатии на модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| Function(View view) callback | Вызываемая функция |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("СамоБан", false, true, ModuleCategory.OTHER);

module.setOnToggleListener(function() {
    LocalPlayer.sendChatMessage("/ban " + LocalPlayer.getNameTag()); // код скорее всего не сработает
}); // Функция будет вызвана, когда произойдёт активация модуля
```

**Примечание:** метод активируется, даже если модуль является включаемым (см. `module.isToggleable()`)
</details>


# Модуль: методы (статические)
**Примечание:** в данном статические модули отличаются от обычных тем, что они требуют передачи (активности) модуля как аргумента функции

## `Module.isToggleable(String moduleName);`
**Описание:** определяет, можно ли включить модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `Boolean isToggleable`

**Пример:**
```js

```
</details>

## `Module.isBindable(String moduleName);`
**Описание:** определяет, можно ли забиндить модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `Boolean isBindable`

**Примеры:**
```js
var module = new Module("АдминЧекер", true, true, ModuleCategory.MISC);

Module.isBindable("АдминЧекер"); // true
```
```js
var module = new Module("UI-картинка", true, false, ModuleCategory.MISC);

Module.isBindable("UI-картинка"); // false
```
</details>

## `Module.getCategory(String moduleName);`
**Описание:** определяет категорию модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `String categoryName`

**Примеры:**
```js
var module = new Module("Краш", true, true, ModuleCategory.OTHER);

Module.getCategory("Краш"); // "Other"
```
</details>

## `Module.isActive(String moduleName);`
**Описание:** определяет, включён ли модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `Boolean isActive`

**Пример:** нет
</details>

## `Module.isBindActive(String moduleName);`
**Описание:** определяет, можно ли включить модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `Boolean isBindActive`

**Пример:** нет
</details>

## `Module.isBindActive(String moduleName);`
**Описание:** определяет, можно ли включить модуль
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `Boolean isBindActive`

**Пример:** нет
</details>

## `Module.hasSettings(String moduleName);`
**Описание:** определяет, есть ли настройки у модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `Boolean hasSettings`

**Пример:**
```js
var module = new Module("Уничтожитель телефона", false, true, ModuleCategory.OTHER);

module.hasSettings(); // false

var setting = new ButtonSetting("Запуск", function(view) {
    // Ещё не сделано ¯\_(ツ)_/¯
});
module.addSetting(setting);

module.hasSettings(); // true
```
</details>

## `Module.getSettingNames(String moduleName);`
**Описание:** даёт названия всех настроек модуля
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |

**Возвращает:** `String[] settingNames`

**Пример:**
```js
var module = new Module("What you know about rolling down in the deep", false, false, ModuleCategory.OTHER);

module.getSettingNames(); // []

var setting = new StateSetting("When your brain goes numb", true);
module.addSetting(setting);

module.getSettingNames(); // ["When your brain goes numb"]
```
</details>
