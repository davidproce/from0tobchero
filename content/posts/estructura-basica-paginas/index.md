---
title: "Base técnica AL - Páginas en Business Central"
date: 2025-08-15
author: "David"
weight: 3
tags: ["MB_820", "Técnico"]
categories: ["MB_820"]
summary: "El primer paso de todo desarrollador es crear páginas en Business Central, vamos a entender los conceptos básicos."
featuredImage: "pages.jpg"  
---
  # Estructura básica de las páginas en Business Central (SaaS)
  
  Este post no es para empaparte de toda la teoría del Learn, sino para que en pocos minutos entiendas **lo esencial** y empieces a crear páginas en AL.
  
  ---
  
  ## 1) Lo mínimo para una página de lista
  
  Podemos empezar creando la página con el snippet `tpage`, que ya te deja preparada la estructura básica para definir tu `PageType`, `SourceTable` y `layout`.
  
  ```al
  page 50200 "Buildings List"
  {
      PageType = List;
      SourceTable = Buildings;
      ApplicationArea = All;
  
      layout
      {
          area(content)
          {
              repeater(General)
              {
                  field("Code"; Rec."Code") { ApplicationArea = All; }
                  field(Name; Rec.Name) { ApplicationArea = All; }
                  field(Status; Rec.Status) { ApplicationArea = All; Caption = 'Estado'; }
              }
          }
      }
  }
  ```
  
  ---
  
  ## 2) Vistas rápidas
  
  ```al
  views
  {
      view(Activos)
      {
          Caption = 'Edificios activos';
          Filters = where(Status = const(Open));
      }
      view(Cerrados)
      {
          Caption = 'Edificios cerrados';
          Filters = where(Status = const(Closed));
      }
  }
  ```
  
  ---
  
  ## 3) Acciones básicas y `Promoted`
  
  ```al
  pageextension 50200 "Building Card Ext" extends "Building Card"
  {
      actions
      {
          addlast(Processing)
          {
              action(ProgramInspection)
              {
                  Caption = 'Programar inspección';
                  Image = Calendar;
                  ApplicationArea = All;
                  Promoted = true;                  //Muestra el botón en la Ribbon
                  PromotedCategory = Process;       //Lo agrupa en la categoría indicada
  
                  trigger OnAction()
                  begin
                      Message('Inspección programada para %1', Rec.Name);
                  end;
              }
          }
      }
  }
  ```
  
  ---
  
  ## 4) Reutilizar acciones con `actionref`
  
  ```al
  actions
  {
      addfirst(Category_Process)
      {
          actionref(QuickInspect; ProgramInspection) { }
      }
  }
  ```
  
  ---
  
  ## 5) Tips rápidos
  
  * Usa `ApplicationArea = All` o no verás nada.
  * Las `views` van fuera del `layout`.
  * Dobles comillas para campos/objetos, simples para textos.
  * Empieza con el snippet `tpage` para ahorrar tiempo.
  
  ---
  
  Con esto puedes montar tu primera página en menos de 10 minutos, con vistas rápidas y acciones bien posicionadas gracias a `Promoted` y `actionref`.
