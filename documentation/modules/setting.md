# Модуль: методы (статические)

## `Setting.getType(String moduleName, String settingName);`
**Описание:** определяет тип настройки
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |

**Возвращает:** ``String moduleType``

**Пример:**
```js
module = new Module("DeathCoords", true, false, ModuleCategory.PLAYER);
module.addSetting(new SliderSetting("Delay", [0.0, 0.0, 3.0, 0.1]));

Setting.getType("DeathCoords", "Delay"); // "Slider"
```
</details>

## `Setting.isVisible(String moduleName, String settingName);`
**Описание:** определяет, видима ли настройка
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |

**Возвращает:** ``Boolean isVisible``

**Пример:**
```js
Setting.isVisible("FastUnban", "Random"); // false (по умолчанию настройки не видно)
```
</details>

## `Setting.setVisibility(String moduleName, String settingName);`
**Описание:** устанавливает (не-)видимость настройке
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |
| Boolean visibility | Видимость настройки |

**Пример:**
```js
Setting.setVisibility("ChestStealer", "Auto close", true); // настройка теперь видима (соответственно, настройка "Close delay" - тоже)
```
</details>

## `Setting.getCurrentMode(String moduleName, String settingName);`
**Описание:** возвращает режим настройки
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |

**Примечание:** требует, чтобы тип настройки был ModeSetting

**Пример:**
```js
Setting.getCurrentMode("KillAura", "Mode"); // настройка теперь видима (соответственно, настройка "Close delay" - тоже)
```
</details>

дальше лень делать
