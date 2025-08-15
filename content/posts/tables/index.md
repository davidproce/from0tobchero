---
title: "Base técnica AL - Tablas - Clasificación y propósito en Business Central"
date: 2025-08-04
author: "David"
weight: 2
tags: ["MB_820", "Técnico"]
categories: ["MB_820"]
summary: "Clasificación funcional de las tablas en BC + herramientas interactivas para dominar las 50 más importantes"
resources:
featuredImage: "tables.png"  
---

  # Tipos de Tablas: Clasificación y propósito en Business Central   

   Como desarrolladores en **AL**, es fundamental entender cómo se organizan las tablas en **Business Central**. Esta clasificación funcional nos ayuda a comprender el propósito de cada tabla y cómo interactúan entre sí en el sistema.   

   ## Datos Principales   


   ### Master Tables (Tablas Maestras)   
   * **Propósito**: Son el núcleo del sistema, contienen la información fundamental del negocio   
   * **Ejemplos**: Customer, Vendor, Item, G/L Account   
   * **Características**: Datos relativamente estables, alta frecuencia de consulta   

   ### Supplementary Tables (Tablas Suplementarias)   
   * **Propósito**: Proporcionan apoyo y configuración a las tablas maestras   
   * **Ejemplos**: Currency, Country/Region, Payment Terms   
   * **Uso**: Validaciones, listas desplegables, configuraciones globales   

   ### Subsidiary Tables (Tablas Subsidiarias)   
   * **Propósito**: Crean enlaces y relaciones entre tablas maestras   
   * **Ejemplos**: Item Vendor, Customer Price Group, Vendor Item No.   
   * **Función**: Establecen relaciones many-to-many entre entidades principales   

   ## Configuración   


   ### Setup Tables (Tablas de Configuración)   
   * **Propósito**: Definen las reglas y comportamientos del sistema   
   * **Ejemplos**: General Ledger Setup, Sales & Receivables Setup, No. Series   
   * **Características**: Una sola empresa, críticas para el funcionamiento   

   ## Transacciones   


   ### Document Tables (Tablas de Documentos)   
   * **Propósito**: Almacenan documentos activos en proceso   
   * **Ejemplos**: Sales Header, Purchase Header, Production Order   
   * **Estado**: Documentos no contabilizados, pueden modificarse   

   ### Journal Tables (Tablas de Diarios)   
   * **Propósito**: Borradores antes de la contabilización   
   * **Ejemplos**: Gen. Journal Line, Item Journal Line   
   * **Función**: Preparación y validación antes del posting   

   ## Histórico   


   ### Document History (Histórico de Documentos)   
   * **Propósito**: Versiones archivadas de documentos contabilizados   
   * **Ejemplos**: Sales Invoice Header, Purch. Rcpt. Header   
   * **Características**: Solo lectura, auditoría y consulta   

   ### Ledger Tables (Tablas de Mayor)   
   * **Propósito**: Transacciones oficiales contabilizadas   
   * **Ejemplos**: G/L Entry, Customer Ledger Entry, Item Ledger Entry   
   * **Importancia**: Base para todos los reportes financieros   

   ### Register Tables (Tablas de Registro)   
   * **Propósito**: Resúmenes y agrupaciones de contabilizaciones   
   * **Ejemplos**: G/L Register, Item Register   
   * **Función**: Trazabilidad y auditoría de procesos de posting   


   ## Herramientas de Aprendizaje   

   Para dominar las **50 tablas más importantes** de Business Central, recomiendo utilizar:   

 ## 🛠️ Herramientas de Aprendizaje

¿Quieres practicar de forma interactiva? Tenemos herramientas especiales para ti:

{{< raw >}}
<div style="background: #f8f9fa; 
            border: 1px solid #e9ecef;
            padding: 1.5rem; 
            margin: 1rem 0; 
            border-radius: 8px; 
            text-align: center;">
    
    <h4 style="margin-bottom: 1rem; color: #495057;">
        📚 Domina las Tablas de Business Central
    </h4>
    
    <p style="margin-bottom: 1.5rem; color: #6c757d; font-size: 0.9rem;">
        Herramientas interactivas para aprender las tablas más importantes
    </p>
    
    <div style="display: flex; gap: 0.8rem; justify-content: center; flex-wrap: wrap;">
        <a href="/apps-tools/tablas-referencia.html" 
           style="background: #28a745; 
                  color: white; 
                  padding: 0.6rem 1.2rem; 
                  text-decoration: none; 
                  border-radius: 5px; 
                  font-size: 0.9rem;
                  font-weight: 500;">
            📊 Referencia
        </a>
        
        <a href="/apps-tools/quiz-tablas.html" 
           style="background: #007bff; 
                  color: white; 
                  padding: 0.6rem 1.2rem; 
                  text-decoration: none; 
                  border-radius: 5px; 
                  font-size: 0.9rem;
                  font-weight: 500;">
            🧠 Quiz
        </a>
        
        <a href="/apps-tools/flashcards-tablas.html" 
           style="background: #fd7e14; 
                  color: white; 
                  padding: 0.6rem 1.2rem; 
                  text-decoration: none; 
                  border-radius: 5px; 
                  font-size: 0.9rem;
                  font-weight: 500;">
            🃏 Flashcards
        </a>
    </div>
    
    <div style="margin-top: 1rem;">
        <a href="/apps-tools/" 
           style="color: #6c757d; 
                  text-decoration: none; 
                  font-size: 0.8rem;">
            Ver todas las herramientas →
        </a>
    </div>
</div>
{{< /raw >}}
