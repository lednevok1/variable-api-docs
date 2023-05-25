# ModuleManager: методы
## `ModuleManager.addModule(Module module)`
**Описание:** добавляет модуль в меню клиента
<details>
<summary>Доп. информация</summary>
 
**Аргументы:**

| Аргумент | Описание |
| ------------- | ------------- |
| Module module | Нужный модуль |

**Возвращает:** нет

**Пример:**
```js
var module = new Module("AutoLava", true, true, ModuleCategory.PLAYER);
ModuleManager.addModule(module);
```
</details>
