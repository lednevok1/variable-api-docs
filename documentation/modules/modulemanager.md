# ModuleManager: методы
## `ModuleManager.addModule(Module module);`
**Описание:** добавляет модуль в меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| -------- | -------- |
| Module module | Модуль |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("АвтоЛава", true, true, ModuleCategory.PLAYER);
ModuleManager.addModule(module);
```
</details>

## `ModuleManager.addModules(Module[] modules);`
**Описание:** добавляет модули в меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| -------- | -------- |
| Module[] modules | Массив модулей |

**Возвращает:** нет

**Пример:**
```js
var module1 = new Module("Подбор пароля", true, true, ModuleCategory.MISC);
var module2 = new Module("Поиск эксплойтов", true, true, ModuleCategory.MISC);
ModuleManager.addModules([module1, module2]);
```
</details>

## `ModuleManager.removeModule(Module module);`
**Описание:** удаляет модуль из меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| -------- | -------- |
| Module module | Модуль |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("АвтоЛава", true, true, ModuleCategory.PLAYER); ModuleManager.addModule(module);

ModuleManager.removeModule(module);
```
</details>

## `ModuleManager.removeModules(Module[] modules);`
**Описание:** удаляет модули из меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:**

| Аргумент | Значение |
| -------- | -------- |
| Module[] modules | Массив модулей |

**Возвращает:** нет

**Пример:**
```js
var module1 = new Module("Подбор пароля", true, true, ModuleCategory.MISC); ModuleManager.addModule(module1);
var module2 = new Module("Поиск эксплойтов", true, true, ModuleCategory.MISC); ModuleManager.addModule(module2);

ModuleManager.removeModules([module1, module2]);
```
</details>

## `ModuleManager.getModuleNames();`
**Описание:** даёт названия всех модулей в меню клиента
<details>
<summary>Доп. информация</summary>

**Аргументы:** нет

**Возвращает:** массив с названиями модулей

**Пример:**
```js
ModuleManager.getModuleNames(); // AimBot, AntiBot... Script manager
```
</details>
