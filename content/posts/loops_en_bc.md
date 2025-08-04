---
title: "Base técnica AL"
date: 2025-08-03
author: "David"
tags: ["MB_820", "Técnico"]
categories: ["MB_820"]
summary: "¡Conociendo Loops en BC!"
resources:
  - name: "featured-image"
    src: "/images/mi-imagen.jpg"  
---

# Loops: Diferentes tipos y aplicaciones

Como ya sabemos, los **loops** son muy importantes en programación; son la pieza fundamental para empezar a programar. Ahora vamos a ver cómo se construyen en **AL**.
![Descripción de la imagen](images/loops.jpg)
## For Básico (Contador)

* **Propósito**: Iterar un número específico de veces  
* **Uso**: Para iteraciones numéricas fijas

```al
procedure CalculateInterest()
var
    Counter: Integer;
    Amount: Decimal;
    InterestRate: Decimal;
begin
    Amount := 1000;
    InterestRate := 0.05;
    for Counter := 1 to 5 do begin
        Amount := Amount * (1 + InterestRate);
        Message('Año %1: Amount = %2', Counter, Amount);
    end;
end;
```
## For con DownTo

**Propósito**: Iterar en orden descendente
**Uso**: Procesar datos en reversa (prioridades, limpieza)

```al
for Counter := StartValue downto EndValue do begin
    // ...  
end;
```

## For con Records (FindSet)

**Más usado**

* **Propósito**: Itera sobre registros que cumplen un filtro

```al
if Record.FindSet() then
    repeat
        // procesar registro
    until Record.Next() = 0;
```

## For con Arrays y Listas

**Iterar sobre colecciones en memoria**

### Array

```al
for i := 1 to ArrayLen(MyArray) do begin
    // procesar MyArray[i]
end;
```

### Lists

```al
foreach Item in ItemList do begin
    // procesar item
end;
```

## For Anidados

* **Propósito**: Bucle dentro de otro para procesos complejos
* **Ejemplo**: Recorrer clientes y dentro recorrer productos
* **Uso**: Generar matrices o configuraciones cruzadas

## Control de Flujos

* **Break**: Para salir del flujo anticipadamente
* **Continue**: No existe continue explícito , se simula con condiciones

## Optimización y Buenas Prácticas

* Usar **SetFilter** para reducir registros antes de iterar
* Usar **SetLoadFields** para cargar solo campos necesarios
* Manejar errores con **try...catch**
* Controlar condiciones para evitar bucles infinitos
* Usar **Commit()** en procesos largos para liberar recursos