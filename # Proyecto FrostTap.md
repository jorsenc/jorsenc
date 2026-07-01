# Proyecto FrostTap
## Máquina automática de vasos congelados para cerveza

**Versión:** 0.1 (Concepto inicial)  
**Autor:** Jorge  
**Estado:** Diseño conceptual

---

# Objetivo

Diseñar una máquina capaz de mantener siempre disponibles varios vasos perfectamente fríos y listos para servir cerveza.

El usuario únicamente debe introducir el vaso utilizado. La máquina realiza automáticamente un aclarado con agua, almacena el vaso en una cámara de congelación y mantiene un stock permanente de vasos listos para utilizar.

El objetivo es eliminar completamente la necesidad de lavar manualmente o enfriar previamente los vasos.

---

# Filosofía del proyecto

El proyecto se basa en cuatro principios:

- Simplicidad mecánica.
- Mantenimiento mínimo.
- Consumo energético reducido.
- Experiencia de usuario instantánea.

No pretende sustituir a un lavavajillas convencional.

Su finalidad es mantener vasos de cerveza siempre preparados.

---

# Funcionamiento

## Paso 1

El usuario termina la cerveza.

## Paso 2

Introduce el vaso boca abajo.

## Paso 3

La máquina detecta el vaso.

## Paso 4

Se realiza un aclarado mediante agua a presión.

No se utilizan:

- detergentes
- jabón
- productos químicos

Únicamente agua.

## Paso 5

El vaso pasa automáticamente al compartimento refrigerado.

## Paso 6

Permanece almacenado hasta alcanzar la temperatura de servicio.

## Paso 7

Cuando el usuario necesita un vaso, simplemente lo retira de la salida.

---

# Flujo

```text
Usuario

    │
    ▼

Introduce vaso boca abajo

    │
    ▼

Aclarado con agua

    │
    ▼

Congelación

    │
    ▼

Almacén FIFO

    │
    ▼

Salida de vaso congelado
```

---

# Componentes principales

## 1. Entrada

Abertura superior.

Características:

- admite un único vaso
- detección automática
- guía centradora

---

## 2. Sistema de aclarado

Compuesto por:

- bomba de agua
- boquillas interiores
- boquillas exteriores

Objetivo:

Eliminar restos de cerveza y espuma.

Duración aproximada:

5-10 segundos.

---

## 3. Refrigeración

Congelador mediante compresor.

Temperatura objetivo:

-18 °C

El aire frío circula continuamente alrededor de los vasos.

---

## 4. Almacén

Capacidad inicial:

6 vasos.

Diseñado como un carrusel giratorio.

Cada alojamiento mantiene el vaso boca abajo.

---

## 5. Dispensador

El usuario extrae un vaso desde la parte inferior.

El sistema entrega siempre el vaso más antiguo.

Sistema FIFO.

---

# Arquitectura

```text
        ┌──────────────────────┐
        │ Entrada de vasos     │
        └──────────┬───────────┘
                   │
                   ▼
        ┌──────────────────────┐
        │ Aclarado con agua    │
        └──────────┬───────────┘
                   │
                   ▼
        ┌──────────────────────┐
        │ Carrusel refrigerado │
        │      (-18 ºC)        │
        └──────────┬───────────┘
                   │
                   ▼
        ┌──────────────────────┐
        │ Salida de vasos      │
        └──────────────────────┘
```

---

# Sistema FIFO

Los vasos se almacenan siguiendo el principio:

First In - First Out.

El primer vaso que entra es el primero que sale.

Ventajas:

- uso uniforme
- congelación homogénea
- rotación automática

---

# Sensores

## Sensor de presencia

Detecta la introducción del vaso.

---

## Sensor de temperatura

Controla la temperatura interior.

---

## Sensor de nivel de agua

Evita funcionamiento sin agua.

---

## Sensor de puerta

Evita pérdidas de frío.

---

# Electrónica

Microcontrolador recomendado:

- ESP32

Funciones:

- control del motor
- lectura de sensores
- control del compresor
- interfaz de usuario

---

# Interfaz

Pantalla frontal.

Información mostrada:

```
Temperatura

-18°C

Vasos disponibles

6

Estado

LISTO
```

---

# Dimensiones estimadas

Altura

60 cm

Anchura

40 cm

Profundidad

40 cm

Capacidad

6 vasos.

---

# Materiales

Exterior

Acero inoxidable.

Interior

ABS alimentario.

Soportes

Aluminio.

Boquillas

Acero inoxidable.

Aislamiento

Espuma de poliuretano.

---

# Consumo

Agua por ciclo

≈ 200 ml

Electricidad

Similar a un pequeño congelador doméstico.

---

# Mantenimiento

Vaciar depósito de agua.

Limpiar filtros.

Revisar boquillas.

Nada más.

---

# Posibles mejoras futuras

## Luz UV-C

Desinfección adicional.

---

## Ozono

Eliminación de olores.

---

## App móvil

Mostrar:

- temperatura
- número de vasos
- avisos

---

## Detección automática del tipo de vaso

Adaptación de la posición según:

- caña
- pinta
- copa
- jarra

---

## Fabricador de hielo integrado

Para otros usos.

---

## Modo ECO

Reduce el consumo cuando no hay uso.

---

# Público objetivo

## Doméstico

Amantes de la cerveza.

---

## Bares

Servicio rápido.

---

## Cervecerías

Mayor calidad de presentación.

---

## Restaurantes

Optimización del servicio.

---

# Ventajas competitivas

- Vasos siempre congelados.
- Funcionamiento automático.
- Sin detergentes.
- Poco mantenimiento.
- Bajo consumo.
- Diseño compacto.
- Experiencia premium.

---

# Principios de diseño

1. El usuario nunca espera.

2. El vaso siempre permanece boca abajo.

3. El proceso debe ser totalmente automático.

4. El mantenimiento debe ser mínimo.

5. El número de piezas móviles debe reducirse al máximo.

6. La máquina debe funcionar de manera continua manteniendo siempre un stock de vasos listos para servir.

---

# Próximas fases del proyecto

- Diseño CAD del mecanismo.
- Diseño del carrusel FIFO.
- Diseño hidráulico del sistema de aclarado.
- Diseño del sistema frigorífico.
- Diseño electrónico.
- Prototipo funcional.
- Pruebas de consumo.
- Optimización industrial.
- Estudio de patentabilidad.