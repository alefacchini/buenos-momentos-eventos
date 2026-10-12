# Buenos Momentos Eventos · Presupuestador Gastronómico Inteligente

> Herramienta de gestión financiera, escandallo simplificado y costeo de servicios de catering.  
> **Trabajo Final Integrador** — Diplomatura Universitaria Superior en Inteligencia Artificial Aplicada a la Gestión de Organizaciones  
> **Facultad de Ciencias Económicas · Universidad de Buenos Aires (FCE-UBA)** · Cohorte 2026

---

## 📌 ¿Qué hace el proyecto?

**Buenos Momentos Eventos** es una aplicación web (*Single Page Application*) desarrollada para resolver de manera simple las fallas y omisiones en el cálculo de costos en emprendimientos gastronómicos familiares.

El sistema procesa automáticamente:
1. **Materia prima de alimentos:** Menús base por comensal y recargos diferenciales para comensales celíacos / sin TACC.
2. **Personal técnico de cocina:** Cálculo discriminado entre cocineros familiares y ayudantes externos, contratados por jornada completa (8 hs) o por horas de producción.
3. **Personal de salón (Mozos):** Sugerencia algorítmica de mozos según comensales y tipo de servicio (al plato, finger food o buffet), discriminando atención familiar de personal contratado afuera.
4. **Logística y transporte:** Estimación de combustible para vehículo utilitario (Fiat Toro 1.3T Nafta: 8.5 km/l + 30% desgaste) o tarifa fija por flete externo.
5. **Costos invisibles:** Detección de descartables, garrafas/gas envasado, fondo de roturas de vajilla y artículos de limpieza.
6. **Margen financiero real:** Aplicación de la fórmula económica $Precio = Costo / (1 - Margen)$ sobre el valor de venta.
7. **Control Humano (*Human-in-the-loop*):** Casillas de verificación para que la familia decida si traslada o absorbe el costo de su propia mano de obra, visibilizando el ahorro cedido al cliente.

---

## 🎯 ¿Para qué sirve?

* **Reduce los tiempos de respuesta:** Pasa de 2 horas de cálculos manuales con papel y calculadora a cotizaciones completas en menos de 3 minutos.
* **Elimina la autoexplotación familiar:** Visibiliza el costo del trabajo propio de los integrantes del emprendimiento, evitando la falsa percepción de ganancia.
* **Protege frente a la inflación:** Fija una vigencia de oferta (predeterminada) con una seña sugerida y cláusula de reajuste del saldo por Canasta Básica de Alimentos o IPC.
* **Profesionaliza la venta:** Permite emitir una propuesta formal imprimible/PDF con membrete institucional para evitar cotizaciones informales por WhatsApp.

---

## ⚙️ Arquitectura de la Solución (Costo Operativo $0)

El proyecto está diseñado bajo una arquitectura ligera y escalable que no genera costos de mantenimiento:

* **Frontend:** HTML5, CSS3 moderno y JavaScript Vanilla (sin frameworks pesados ni dependencias externas).
* **Persistencia Local:** `localStorage` del navegador y descarga de archivos de configuración en formato `.json`.
* **Backend Cloud:** Endpoint serverless en Google Apps Script que añade automáticamente cada cotización emitida a una hoja de cálculo en Google Sheets.

---

## 🚀 ¿Cómo se usa?

### 1. Pestaña: Configuración de Tarifas
* Se ingresa el **Valor Hora Base** (anclado habitualmente a la referencia del servicio doméstico).
* Se configuran los **multiplicadores salariales**: Cocinero (`1.5`), Ayudante (`1.2`) y Mozo (`1.1`).
* Se revisan los costos de menús por persona, combustible, porcentajes de costos invisibles y margen comercial deseado.
* Se presiona **Guardar Configuración de Tarifas**. Los datos quedan memorizados en el dispositivo.
* *(Opcional)* Se puede descargar una copia de seguridad con el botón **Respaldar Parámetros (JSON)** para trasladar los valores a otra computadora o celular.

### 2. Pestaña: Ficha del Servicio
* Se completan los datos del evento: cliente, cantidad de comensales y tipo de menú (Formal, Finger Food o Buffet).
* Se ingresa si existen comensales con menús especiales (celíacos / sin TACC).
* Se define el personal de cocina (cuántos familiares y cuántos ayudantes externos, por horas o por jornadas completas).
* Se revisa la dotación sugerida de mozos y las horas de duración del evento (por defecto 6 hs).
* Se seleccionan las condiciones logísticas (vehículo propio indicando kilómetros o contratación de flete externo).
* Se presiona **Calcular Cotización**.

### 3. Pestaña: Cotización & Decisiones
* El sistema muestra el desglose completo del costo directo, logístico e invisible.
* **Panel de Control Familiar:** Permite marcar o desmarcar el cobro de la mano de obra propia. Si la familia decide no cobrarse, el calculador advierte cuánto dinero propio están absorbiendo para beneficiar al cliente.
* Muestra el precio sugerido por comensal, el precio final y la seña requerida (20%).
* **Acciones disponibles:**
  * **Guardar en Google Sheets:** Envía el registro a la planilla compartida en la nube.
  * **Imprimir Presupuesto Formal (PDF):** Genera la vista limpia comercial lista para enviar al cliente.

---

## 📂 Estructura del Repositorio

```text
├── index.html              # Aplicación web completa (Frontend + Lógica de cálculo)
├── logo.png                # Isologotipo oficial de Buenos Momentos Eventos
├── backend.gs              # Código de Google Apps Script para recibir datos en Sheets
├── README.md               # Documentación general del proyecto (este archivo)
└── docs/
    └── Informe_Final.pdf   # Documento académico formal para la FCE-UBA
