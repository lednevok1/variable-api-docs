# Настройка (селектор): конструктор
```js
ModeSetting(String name, String[] modes);
```

# Настройка (кнопка): методы
## ``ModeSetting.getName();``
**Описание:** получает имя настройки

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ButtonSetting setting | Имя настройки |

**Возвращает:** ``String settingName``

**Пример:**
```js
var setting = new ModeSetting("Nuke USA", function() {
    Memory.read(0, 1);
});

setting.getName(); // "Nuke USA"
```
</details>

## ``ModeSetting.getType();``
**Описание:** возвращает тип настройки ("mode")

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ModeSetting setting | Настройка |

**Возвращает:** ``String settingType``

**Пример:**
```js
var setting = new ModeSetting("Приоритет", ["Расстояние", "ХП", "ФОВ"]);

setting.getType() // "mode"
```
</details>

## ``ModeSetting.isVisible();``
**Описание:** Определяет видимость настройки

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ModeSetting setting | Настройка |

**Возвращает:** ``Boolean isVisible``

**Пример:**
```js
var setting = new ModeSetting("Способ", ["Падение с высоты", "Телепортация в пустоту", "Команда", "Установка ХП"]);

setting.isVisible(); // true
```

</details>

## ``modeSetting.setVisibility(Boolean visibility);``
**Описание:** Устанавливает (не-)видимость настройке

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ModeSetting setting | Настройка |
| Boolean visibility | Видимость настройки |

**Пример:**
```js
var setting = new ModeSetting("Режим", ["Телепорт", "Скорость"]);

setting.setVisibility(false); // модуль типа не видна типерь
```

</details>

## ``ModeSetting.getCurrentMode();``
**Описание:** определяет текущий режим настройки

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ModeSetting setting | ВСТАВЬТЕ ОПИСАНИЕ |

**Возвращает:** ``String mode``

**Пример:**
```js
var setting = new ModeSetting("Место сброса ядерной бомбы", ["Украина", "США", "Россия", "Польша", "Узбекистан"]);

ModeSetting.getCurrentMode(); // "Украина", если ранее не менялось
```

</details>

## ``ModeSetting.setOnModeSelectedListener(Function callback);``
**Описание:** Устанавливает действие при выборе режима настройки

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ModeSetting setting | ВСТАВЬТЕ ОПИСАНИЕ |
| Function callback | ВСТАВЬТЕ ОПИСАНИЕ |

**Пример:**
```js
var setting = new ModeSetting("ТОЧНО КРАШНУТЬ ИГРУ?", ["Да", "Нет"]);

ModeSetting.setOnModeSelectedListener(function(mode) {
    if (mode == "Да") {
        Memory.getString(0, 1);
    }
});
```

</details>
