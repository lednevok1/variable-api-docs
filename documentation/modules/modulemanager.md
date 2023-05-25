# ModuleManager: методы
## `ModuleManager.addModule(Module module)`
**Описание:** добавляет модуль в меню клиента
<details>
<summary>Доп. информация</summary>

### Аргументы

| Аргумент | Значение |
| ------------- | ------------- |
| Module module | Модуль, который надо добавить |

**Возвращает:** нет

**Пример:**
```
var module = new Module("AutoLava", true, true, ModuleCategory.PLAYER);
ModuleManager.addModule(module);
```
</details>
