# Buenos Momentos Eventos · Presupuestador Gastronómico Inteligente

<p align="center">
  <img src="logo.png" alt="Buenos Momentos Eventos" width="220">
</p>

<p align="center">
  <strong>Herramienta de gestión financiera, escandallo simplificado y costeo de servicios de catering.</strong><br>
  <em>Trabajo Final Integrador — Diplomatura Universitaria Superior en Inteligencia Artificial Aplicada a la Gestión de Organizaciones</em><br>
  <strong>Facultad de Ciencias Económicas · Universidad de Buenos Aires (FCE-UBA)</strong> · Cohorte 2026
</p>

---

## 📌 ¿Qué hace el proyecto?

**Buenos Momentos Eventos** es una aplicación web local (*Single Page Application*) desarrollada para resolver las fallas de costeo, omisión de gastos operativos e invisibilización de la mano de obra en un emprendimiento familiar de catering.

El sistema procesa y calcula de forma autónoma:
1. **Materia prima y menús:** Selección de propuestas gastronómicas (Formal 3 Pasos, Finger Food, Buffet Criollo o Personalizado) con cálculo diferencial automático para comensales celíacos / Sin TACC (+35% por protocolo de elaboración cuidada).
2. **Personal de cocina discriminado:** Cálculo individualizado entre **Cocineros Familiares**, **Cocineros Externos** (tarifa chef calificado $\times 1.5$) y **Ayudantes Externos** ($\times 1.2$), contratados por jornadas completas (8 hs) o por horas directas de producción.
3. **Personal de salón (Mozos):** Sugerencia algorítmica de dotación según tipo de servicio (al plato: 1/24, finger food: 1/35, buffet: 1/40), distinguiendo atención familiar de mozos externos contratados ($\times 1.1$).
4. **Logística y traslado:** Estimación de combustible para vehículo utilitario (Fiat Toro 1.3T Nafta: 8.5 km/l + 30% de amortización/desgaste) o cotización fija mediante flete contratado.
5. **Insumos invisibles detallados:** Detección y prorrateo automático de **Descartables y Gas envasado** (10%), **Limpieza e higiene** (2%) y **Otros** (roturas de vajilla, reposición de cristalería y contingencias: 3%).
6. **Margen financiero real sobre venta:** Aplicación del principio contable:
   $$\text{Precio Final} = \frac{\text{Costo Total}}{1 - \text{Margen}}$$
7. **Control Humano (*Human-in-the-loop*):** Panel interactivo donde la familia decide qué tareas propias facturar y cuáles ceder, visibilizando en pantalla el monto exacto absorbido para evitar la autoexplotación familiar.
8. **Generador de Propuesta Comercial (PDF):** Sistema de impresión desacoplado en formato A4 (15 mm de margen perimetral) calibrado para emitir presupuestos limpios en 1 sola carilla, compatible con PC y navegadores móviles (Android/iOS), sin exponer costos internos ni márgenes confidenciales.

---

## 🔍 Relevamiento Metodológico y Estándares de la Industria

El diseño funcional y los algoritmos de cálculo de esta herramienta se fundamentan en dos pilares clave de gestión:

1. **Diagnóstico Organizacional (Cuestionario a Operadores):**  
   Se realizó un relevamiento inicial a los responsables del servicio para analizar cómo cotizaban históricamente. El diagnóstico reveló omisiones críticas recurrentes:
   * **Invisibilización de la mano de obra familiar:** Las horas dedicadas por los integrantes de la familia a la elaboración previa, cocción y atención no se contabilizaban como costo, distorsionando la rentabilidad real y provocando autoexplotación económica.
   * **Costos invisibles no recuperados:** Gastos operativos como gas envasado, film, bolsas de vacío, químicos de limpieza y roturas de vajilla eran absorbidos por el emprendimiento sin trasladarse al presupuesto.

2. **Alineación con Estándares Gastronómicos Profesionales:**  
   Los parámetros preconfigurados responden a métricas y buenas prácticas del sector de catering y banquetería:
   * **Escandallo e Insumos Ocultos:** Estimación técnica de descartables (10%), higiene/limpieza (2%) y fondo de rotura/reposición (3%).
   * **Dotación Algorítmica de Salón:** Ratios estándar de mozos por tipo de servicio (1/24 en formal al plato, 1/35 en finger food y 1/40 en buffet).
   * **Estructura Salarial Homologada:** Tarificación referenciada en la hora base de servicio y multiplicadores ponderados por especialidad técnica (Chef $\times 1.5$, Ayudante $\times 1.2$, Mozo $\times 1.1$).
   * **Margen Financiero Real:** Aplicación del principio contable sobre el precio final de venta en lugar del margen sobre costo directo.
---

## 🎯 ¿Para qué sirve?

* **Agiliza los tiempos comerciales:** Reduce el tiempo de presupuestación de más de 2 horas de cálculos manuales a menos de 3 minutos.
* **Transparencia económica familiar:** Cuantifica monetariamente las horas de elaboración y salón aportadas por los integrantes de la familia.
* **Flexibilidad comercial y protección inflacionaria:** Permite definir la vigencia de la oferta mes a mes de forma personalizada (sin plazos predeterminados forzados), calculando un anticipo de seña y estableciendo cláusulas de reajuste del saldo pendiente por IPC o Canasta Básica de Alimentos.
* **Presentación ejecutiva y profesional:** Genera un presupuesto formal listo para descargar y enviar por WhatsApp o correo electrónico, eliminando la informalidad de cotizaciones por mensajes de texto.

---

## ⚙️ Arquitectura Técnica y Portabilidad (Costo Operativo $0)

Diseñado con un enfoque de arquitectura liviana, portable y con costo de mantenimiento cero:
* **Frontend Nativo:** Construido en HTML5 semántico, CSS3 moderno con variables y grillas simétricas adaptables, y Vanilla JavaScript puro (sin frameworks pesados ni dependencias externas frágiles).
* **Almacenamiento Local Autónomo:** Utiliza el motor de `localStorage` del navegador para recordar parámetros y tarifas sin requerir bases de datos remotas ni servidores pagos.
* **Portabilidad y Respaldo de Datos:** Incorpora botones simplificados (*“Respaldar en archivo las configuraciones”* y *“Cargar archivo de configuraciones”*) que generan un archivo de texto descargable en la carpeta local, permitiendo trasladar las tarifas por WhatsApp o mail a cualquier celular o computadora sin complicaciones técnicas.
* **Impresión Desacoplada A4:** Motor CSS `@media print` optimizado que aísla la hoja comercial del resto de la interfaz, asegurando márgenes simétricos y eliminando páginas en blanco innecesarias.

---

## 🚀 ¿Cómo se usa?

1. **Configuración de Tarifas (Pestaña 1):**
   * Se ajusta el Valor Hora Base (referencia salarial anclada a servicio doméstico) y los multiplicadores de oficio.
   * Se fijan los costos de menús, combustible y porcentajes de insumos invisibles.
   * Se guarda la configuración en el dispositivo o se descarga una copia de respaldo.
2. **Ficha del Servicio (Pestaña 2):**
   * Los campos de entrada vienen limpios para evitar confusiones operativas.
   * Se ingresa el cliente, comensales totales, celíacos y tipo de menú.
   * Se completa la dotación de cocina (familiares, cocineros externos y ayudantes) y personal de mozos.
   * Se define si requiere armado previo de salón (4 hs), logística y el plazo de vigencia deseado (definido por el usuario en cada cotización).
   * Se presiona **🧮 Calcular Cotización**.
3. **Cotización & Propuesta Comercial (Pestaña 3):**
   * Se evalúa el desglose de costos directos e invisibles.
   * Se utiliza el panel de decisiones para seleccionar qué mano de obra trasladar al precio de venta.
   * Se presiona **📄 Ver Propuesta Formal para el Cliente (PDF)** y luego **🖨️ Descargar en PDF / Imprimir** para emitir el presupuesto formal.

---

## 🔮 Escalabilidad y Evolución Futura

El proyecto contempla una hoja de ruta estratégica para evolucionar hacia una plataforma de gestión integral:
* **Panel de Control y Métricas (Dashboard KPI):** Visualización de cubiertos vendidos, menús más demandados y facturación mensual proyectada.
* **Módulo de Cobranzas y Financiación:** Seguimiento de señas cobradas, cuotas pactadas y reajuste automático de saldos según índices inflacionarios oficiales (INDEC / CBA).
* **Integración Omnicanal con IA Agéntica:** Asistente conversacional en WhatsApp Business para atención inicial de consultas de eventos y precarga automática de fichas de servicio.
* **Persistencia en la Nube:** Migración planificada hacia bases de datos serverless (Supabase / Firebase) para sincronización multiusuario sin costos fijos.

---

## 📂 Estructura del Repositorio

```text
├── index.html              # Aplicación web completa (Frontend, motor de costeo y módulo de impresión)
├── logo.png                # Isologotipo oficial de Buenos Momentos Eventos
├── README.md               # Documentación general del proyecto (este archivo)
└── docs/
    └── Informe_Final.pdf   # Documento académico formal presentado ante la FCE-UBA
