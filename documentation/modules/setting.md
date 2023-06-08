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

**Возвращает:** ``String settingType``

**Пример:**
```js
module = new Module("DeathCoords", true, false, ModuleCategory.PLAYER);
module.addSetting(new SliderSetting("Delay", [0.0, 0.0, 3.0, 0.1]));

Setting.getType("DeathCoords", "Delay"); // "slider"
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
**Описание:** возвращает режим настройки-режима
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |

**Возвращает:** ``String settingMode``

**Пример:**
```js
Setting.getCurrentMode("KillAura", "Mode"); // "Multi"
```
  
**Примечание:** требует, чтобы тип настройки был ModeSetting
</details>

## `Setting.getCurrentValue(String moduleName, String settingName);`
**Описание:** возвращает значение настройки-слайдера
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |

**Возвращает:** ``Double settingValue``

**Пример:**
```js
Setting.getCurrentValue("Coordinates", "Pos X"); // 0.5
```

**Примечание:** требует, чтобы тип настройки был SliderSettingA
</details>


## `Setting.getText(String moduleName, String settingName);`
**Описание:** возвращает текст из настройки
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |

**Возвращает:** ``String settingText``

**Пример:**
```js
Setting.getCurrentValue("Spammer", "Text"); // "Variable - the best mcpe hacked client!"
```

**Примечание:** требует, чтобы тип настройки был TextFieldSetting
</details>


## `Setting.isActive(String moduleName, String settingName);`
**Описание:** показывает, включена (активна) ли настройка
<details>
<summary>Доп. информация</summary>

**Аргументы:**
| Аргумент | Значение |
| -------- | -------- |
| String moduleName | Название модуля |
| String settingName | Название настройки |

**Возвращает:** ``Boolean isActive``

**Пример:**
```js
Setting.isActive("Flight", "Disable on flight"); // true
```
</details>
