# RESTAURANTE-PRACTICA-PYTHON

Pequeño proyecto para practicar **programación orientada a objetos** en Python: clases, atributos, métodos, herencia y relación entre clases.

## Descripción

El programa modela el menú de un restaurante. Un `Restaurante` contiene varios productos del menú, que pueden ser `Plato` o `Bebida`.

## Estructura de clases

| Clase | Hereda de | Atributos | Métodos |
|---|---|---|---|
| `ProductoMenu` | - | `nombre`, `precio`, `disponible` | `mostrar_info()` |
| `Plato` | `ProductoMenu` | `tipo`, `vegetariano` | `preparar()` |
| `Bebida` | `ProductoMenu` | `tamano_ml`, `alcoholica` | `servir()` |
| `Restaurante` | - | `nombre`, `menu` (lista de productos) | `anadir_producto()`, `mostrar_menu()` |

**Relación:** un `Restaurante` contiene 0 o más `ProductoMenu`.
**Herencia:** `Plato` y `Bebida` heredan de `ProductoMenu` y usan `super().__init__()` para reutilizar sus atributos.

## Ejecución

Requisitos: Python 3.10 o superior.

```bash
python restaurante_corregido.py
```

## Ejemplo de uso

```python
restaurante = Restaurante("Mi Restaurante")
pizza = Plato("Pizza", 10.0, True, "Principal", False)
cola = Bebida("Cola", 2.0, True, 500, False)

restaurante.anadir_producto(pizza)
restaurante.anadir_producto(cola)
restaurante.mostrar_menu()
```

Salida:

```
Nombre: Pizza | Precio: 10.0 | Disponible: True
Nombre: Cola | Precio: 2.0 | Disponible: True
```

## Correcciones respecto a la versión original

- `ProductoMenu` se define antes de usarse en `Restaurante`.
- Se evita el valor por defecto mutable (`menu=[]`) en el constructor.
- Se añade `self` a los métodos `preparar()` y `servir()`.
- Se añade un `__init__` en la clase padre y las hijas lo reutilizan con `super()`.
- Los nombres de métodos y atributos coinciden con el diagrama de clases.

## Autora

Beatriz Iñiguez Cascales
