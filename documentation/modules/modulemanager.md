# ModuleManager: методы
## `ModuleManager.addModule(Module module)`
**Описание:** добавляет модуль в меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| ------------- | ------------- |
| Module module | Модуль |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("АвтоЛава", true, true, ModuleCategory.PLAYER);
ModuleManager.addModule(module);
```
</details>

## `ModuleManager.addModules(Module[] modules)`
**Описание:** добавляет модули в меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| ------------- | ------------- |
| Module[] modules | Массив модулей |

**Возвращает:** нет

**Пример:**
```js
var module1 = new Module("Подбор пароля", true, true, ModuleCategory.PLAYER);
var module2 = new Module("Поиск эксплойтов", true, true, ModuleCategory.MISC);
ModuleManager.addModules([module1, module2]);
```
</details>

## `ModuleManager.addModules(Module[] modules)`
**Описание:** добавляет модули в меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| ------------- | ------------- |
| Module[] modules | Массив модулей |

**Возвращает:** нет

**Пример:**
```js
var module1 = new Module("Подбор пароля", true, true, ModuleCategory.PLAYER);
var module2 = new Module("Поиск эксплойтов", true, true, ModuleCategory.MISC);
ModuleManager.addModules([module1, module2]);
```
</details>
