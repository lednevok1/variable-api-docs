# Настройка (кнопка): конструктор
```js
ButtonSetting(String name, Function callback);
```
**Примечание:** ``Function callback`` имеет аргумент View view

# Настройка (кнопка): методы
## ``ButtonSetting.getName();``
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
setting = new ButtonSetting("Nuke USA", function() {
    Memory.read(0, 1);
});

setting.getName(); // "Nuke USA"
```
</details>

## ``ButtonSetting.getType();``
**Описание:** возвращает тип настройки ("button")

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ButtonSetting setting | Настройка |

**Возвращает:** ``String settingType``

**Пример:**
```js
setting = new ButtonSetting("Run", function() {
    // pass
});

setting.getType() // "button"
```
</details>

## ``ButtonSetting.isVisible();``
**Описание:** Определяет видимость настройки

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ButtonSetting setting | Настройка |

**Возвращает:** ``Boolean isVisible``

**Пример:**
```js
setting = new ButtonSetting("Example", function() {
    // pass
});

setting.isVisible(); // true
```

</details>

## ``ButtonSetting.setVisibility(Boolean visibility);``
**Описание:** Устанавливает (не-)видимость настройке

<details>
<summary>Доп. информация</summary>

**Аргумент(-ы)**:
| Аргумент | Значение |
| -------- | -------- |
| ButtonSetting setting | Настройка |
|  Boolean visibility | Видимость настройки |

**Пример:**
```js
// пример будет потом
```

</details>
