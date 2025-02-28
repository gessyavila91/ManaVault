### **1. Diagnóstico del Código Existente**
Antes de realizar cualquier cambio, realiza un diagnóstico del código existente. Tu caso inicial presentaba varias señales de que era necesario un cambio:
- **Falta de separación de responsabilidades**: Toda la lógica de actualización de productos estaba en una función del objeto principal, lo que dificultaba la lectura y el mantenimiento.
- **No respeta el principio abierto/cerrado (OCP)**: Cada vez que se agregara un nuevo tipo de producto, sería necesario modificar el método `updateQuality`, lo cual no es escalable.
- **Duplicación de Reglas**: El código estaba replicando varias condiciones y lógicas, en lugar de abstraerlas.

Ahora, en tu rama de prueba, se corrigió esto aplicando 

**varios principios del diseño SOLID**.

---
### **2. Cambios Realizados en la Rama de Prueba**
#### **2.1. Principio S: Responsabilidad Única**
- Cada clase ahora tiene una única responsabilidad:
    - La lógica de cada tipo de producto se encapsuló en diferentes clases (`AgedBrieAttributesUpdater`, `BackstagePassesAttributesUpdater`, `ConjuredAttributesUpdater`, etc.).
    - Esto facilita las pruebas unitarias y da mayor flexibilidad para cambios futuros.
#### **2.2. Principio O: Abierto/Cerrado**
- En lugar de modificar la lógica principal en `GildedRose`, ahora se utiliza un **factory** (`ProductUpdaterFactory`) para instanciar la clase adecuada correspondiente al tipo de producto.
    - Si se necesita agregar un nuevo tipo, como "Potion", solo se crea una nueva implementación de `ProductUpdater`.
    - **No es necesario modificar código existente**, cumpliendo con el principio de ser abierto para extensiones, pero cerrado para modificaciones.
#### **2.3. Uso del Polimorfismo (Principio L)**

- Se definió una interfaz genérica `ProductUpdater` que contiene el método `update`. Cada tipo de producto implementa esta interfaz con su propia lógica.
- Esto permite a `GildedRose` delegar la responsabilidad de actualización sin preocuparse por las reglas específicas.
#### **2.4. Principio de Segregación de Interfaces (I)**
- No se obliga a las clases de tipos de productos a implementar métodos que no necesitan. Todas solo implementan `ProductUpdater` con `update`.
#### **2.5. Principio de Inversión de Dependencias (D)**
- `GildedRose` ahora depende de abstracciones (`ProductUpdater`) y no de implementaciones específicas. Esto promueve un diseño que es fácil de modificar y extender.
#### **2.6. Refactorización General**
- Uso de métodos reutilizables para acciones frecuentes (como `increaseQuality`, `isExpired`, etc.), implementados en `AbstractProductAttributesUpdater`.
- Código más limpio, legible y modular.
- Añadiste pruebas de integración y unitarias que validan el comportamiento del sistema, lo que asegura la estabilidad del código después de los cambios.
---
### **3. Proceso Paso a Paso para Implementar Cambios**

#### **Paso 1: Planificación**
- Analiza las limitaciones del código existente que deseas mejorar.
- Define los módulos, clases o componentes que violan principios SOLID o no cumplen con buenas prácticas.
- Planifica la nueva estructura de clases y métodos.
#### **Paso 2: Introducir Interfaces y Clases Abstraídas**
- Crea interfaces como `ProductUpdater` para definir un contrato genérico que las clases específicas implementarán.
- Si ciertas acciones son comunes (como disminuir la fecha de venta o calidad), encapsula estas acciones en una clase abstracta como `AbstractProductAttributesUpdater`.
#### **Paso 3: Implementación de Clases Específicas**
- Crea clases específicas para cada tipo de producto (si es necesario).
- Implementa la lógica específica de cada producto en sus respectivas clases.
    - Ejemplo: `AgedBrieAttributesUpdater` incrementa la calidad, mientras que `ConjuredAttributesUpdater` disminuye la calidad más rápido.
#### **Paso 4: Crear un Factory para Delegar la Instancia Correcta**
- Define una clase fábrica como `ProductUpdaterFactory` que se encargue de devolver la instancia correcta basada en el nombre del producto.
- Usa `match` o `switch` para identificar el tipo de producto y devolver el updater.

``` php
class ProductUpdaterFactory  
{  
    public static function getUpdater(Item $item): ProductUpdater  
    {  
        $name = strtoupper($item->name);  
  
        return match (true) {  
            str_contains($name, 'AGED BRIE') => new AgedBrieAttributesUpdater(),  
            str_contains($name, 'BACKSTAGE PASSES') => new BackstagePassesAttributesUpdater(),  
            str_contains($name, 'CONJURED') => new ConjuredAttributesUpdater(),  
            str_contains($name, 'SULFURAS') => new SulfurasAttributesUpdater(),  
            default => new RegularAttributesUpdater(),  
        };  
    }  
}
```
#### **Paso 5: Modificar la Lógica Principal para Delegar Responsabilidades**
- Cambia el método principal (`updateQuality`) para que delegue la lógica específica de actualización al updater adecuado retornado por el factory.
``` php
public function updateQuality(): void  
{  
    foreach ($this->items as $item) {  
        $updater = ProductUpdaterFactory::getUpdater($item);  
        $updater->update($item);  
    }  
}
```
#### **Paso 6: Probar la Nueva Implementación**
- Realiza pruebas unitarias para cada clase (niveles bajos).
- Realiza pruebas de integración para garantizar que el sistema funciona como debería.
- Asegúrate de cubrir todos los casos del negocio (productos normales, especiales y atípicos).
#### **Paso 7: Documentación**
- Comenta el código.
- Documenta cómo agregar nuevos tipos de productos mediante nuevas clases específicas.
#### **Paso 8: Revisión y Refactorización**
- Evalúa si la implementación sigue siendo legible y adherida a las buenas prácticas.
- Itera sobre el código si notas áreas que puedan mejorar.
---
### **4. Beneficios de Tu Refactorización**
1. **Escalabilidad:** Puedes añadir nuevos productos sin modificar código existente, sólo adicionando clases.
2. **Mantenimiento:** El código es más fácil de entender, modificar y extender.
3. **Pruebas:** Cada clase puede probarse de manera independiente.
4. **Cumplimiento de SOLID**: El código es modular, reutilizable, y más robusto frente a cambios futuros.
5. **Reduce la deuda técnica:** Al aplicar principios sólidos, mejoras la calidad general del sistema.
---
