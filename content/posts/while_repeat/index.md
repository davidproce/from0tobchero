---
title: "Base técnica AL - Loops - While y Repeat until"
date: 2025-08-03
author: "David"
tags: ["MB_820", "Técnico"]
categories: ["MB_820"]
summary: "¡While y Repeat Until!"
featuredImage: "loops.jpg"  

---

##### While y Repeat until: casos y usos prácticos

### For (FindSet + repeat until):
- Lo que hemos visto: `if Record.FindSet() then repeat... until Record.Next() = 0;`
- Es específico para recorrer registros en tablas
- No puedes controlar cuándo va a parar
### While (Evalúa antes de ejecutar)
- Para condiciones que pueden cambiar durante el bucle
- Ejemplo: `while (Counter > 10) and (Found = False) do`
### Repeat - until (Genérico) (Evalúa después de ejecutar)
- Mínimo 1 vez
- Ejemplo: 
```
repeat
    Counter += 1;
until Counter = 10;
```
## Cuándo usar cada uno
| Usa while cuando: | Usa repeat - until cuando: |
|-------------------|----------------------------|
| Puedes no necesitar ejecutar código | Siempre necesitas ejecutar el código |
| La condición puede ser falsa desde el inicio | Validas datos de entrada |
| Navegas por datos hasta encontrar algo | Procesas hasta completar una tarea |
## While
**Generar número único**
```
while Customer.Get(NewCustomerNo) do begin
    Counter += 1;
    NewCustomerNo := 'Cust' + Format(Counter);
end;
```
**Procesar hasta stock suficiente**
```
while (RemainingQty > 0) and (MoreItemsAvailable) do begin
    // Reservar stock
    // Actualizar RemainingQty
end;
```
**Leer archivo línea por línea:**
```
while not FileStream.EOS do begin
    LineText := FileStream.ReadLine();
    ProcessLine(LineText);
end;
```
## Repeat - until
- Evalúa después de ejecutar
**Validar entrada de usuario**
```
repeat
    Amount := StrToDecimal(InputText);
    if Amount <= 0 then
        Message('Debe ser mayor que 0')
until Amount > 0;
```

