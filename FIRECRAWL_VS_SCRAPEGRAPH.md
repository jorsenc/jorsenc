# Comparativa: Firecrawl vs ScrapeGraphAI

## 1. ENFOQUE PRINCIPAL

| Aspecto | Firecrawl | ScrapeGraphAI |
|--------|-----------|---------------|
| **Especialidad** | Web crawling y scraping masivo | Extracción de datos con IA |
| **Filosofía** | "Rastrear sitios completos" | "Extraer lo que pides en lenguaje natural" |
| **Mejor para** | Sitios grandes, mapeo de estructura | Consultas específicas, datos puntuales |

---

## 2. FUNCIONALIDADES CLAVE

### Firecrawl
- ✅ **Crawling recursivo** - Rastrea múltiples páginas automáticamente  
- ✅ **Extracción de enlaces** - Mapea toda la estructura del sitio  
- ✅ **Monitoreo** - Supervisa cambios en tiempo real  
- ✅ **Búsqueda limitada** - Busca dentro de sitios indexados  
- ✅ **Markdown perfecto** - Conversión limpia a markdown  
- ❌ **JSON estructurado** - Requiere esquema predefinido  

### ScrapeGraphAI
- ✅ **Prompts naturales** - "Dame los precios" vs esquema JSON  
- ✅ **JSON automático** - Estructura datos sin esquema  
- ✅ **Búsqueda web completa** - Busca en toda la web  
- ✅ **Multiformat** - HTML, Markdown, JSON, Screenshots, Links  
- ❌ **Crawling limitado** - Mejor para páginas individuales  
- ❌ **Monitoreo débil** - No está optimizado para vigilancia  

---

## 3. CASOS DE USO

### Usa Firecrawl si necesitas:

```
- Scrapear un e-commerce completo (100+ productos)
- Monitorear cambios en un sitio periódicamente
- Mapear la estructura completa de un sitio
- Descargar contenido masivo de Wikipedia, blogs, etc.
- Extraer todos los enlaces de un dominio
```

### Usa ScrapeGraphAI si necesitas:

```
- "Dame el precio del iPhone 16 en este sitio"
- Buscar información en Google, no en un sitio específico
- Extraer datos complejos con prompts naturales
- Comparar precios entre múltiples sitios
- Obtener JSON estructurado sin definir schema
```

---

## 4. VELOCIDAD Y LÍMITES

| Métrica | Firecrawl | ScrapeGraphAI |
|---------|-----------|---------------|
| **Velocidad** | Rápido (optimizado) | Moderado (LLM) |
| **Páginas/sesión** | 100-1000+ | 1-10 típicamente |
| **Timeout** | ~30s por página | ~30s por request |
| **Créditos/uso** | Muy económico | Moderado |
| **Rate limit** | Alto | Moderado |

---

## 5. CALIDAD DE DATOS

| Aspecto | Firecrawl | ScrapeGraphAI |
|--------|-----------|---------------|
| **Precisión estructural** | 95% (reglas predefinidas) | 85-90% (IA) |
| **Campos dinámicos** | ⚠️ Problema | ✅ Maneja bien |
| **JavaScript renderizado** | ✅ Sí | ✅ Sí |
| **Datos complejos** | ⚠️ Necesita regex/parseadores | ✅ Entiende contexto |
| **Robustez a cambios** | ⚠️ Se rompe si cambia HTML | ✅ Adaptable |

---

## 6. EJEMPLO PRÁCTICO

### Firecrawl: Scrapear Amazon

```bash
# Crawl recursivo de toda la categoría
firecrawl crawl "https://amazon.com/s?k=laptop"
# Resultado: 500+ páginas, todos los productos
```

### ScrapeGraphAI: Buscar precios

```
Scrape "https://amazon.com/s?k=laptop" y extrae:
- Top 10 laptops
- Precio actual
- Rating
- En formato CSV
```

---

## 7. COSTO APROXIMADO

| Operación | Firecrawl | ScrapeGraphAI |
|-----------|-----------|---------------|
| 1 página simple | $0.01-0.05 | $0.02-0.10 |
| 100 páginas | $1-5 | Requiere múltiples requests |
| API key gratuita | ✅ Limitada | ✅ Limitada |

---

## 8. AUTENTICACIÓN

| Tipo | Firecrawl | ScrapeGraphAI |
|------|-----------|---------------|
| **Sitios con login** | ⚠️ Soporte limitado | ⚠️ Soporte limitado |
| **Cookies** | ✅ Sí | ✅ Sí |
| **Headers personalizados** | ✅ Sí | ✅ Sí |
| **Proxy** | ✅ Sí | ✅ Sí |

---

## 9. MATRIZ DE DECISIÓN

### Elige Firecrawl si:

- Necesitas datos de muchas páginas (100+)
- Requieres estructura consistente
- Necesitas monitoreo automático
- El sitio es conocido y estable
- Presupuesto limitado para volumen alto

### Elige ScrapeGraphAI si:

- Necesitas flexibilidad y prompts naturales
- Datos varían o estructura es inconsistente
- Necesitas búsqueda web global
- Requieres JSON sin definir esquema
- Datos complejos que necesitan "entendimiento"

---

## 10. HYBRID APPROACH (Lo mejor de ambos)

### Estrategia recomendada:

1. **Usa FIRECRAWL para:**
   - Descargar contenido base
   - Mapear estructura del sitio
   
2. **Usa SCRAPEGRAPH para:**
   - Procesar datos y extraer campos específicos
   - Enriquecer con búsquedas web
   - Transformar a formato final

---

## RESUMEN RÁPIDO

### Firecrawl
- **Fortaleza:** Crawling masivo y eficiente
- **Debilidad:** Requiere esquema predefinido
- **Mejor caso:** E-commerce, Wikipedia, blogs
- **Filosofía:** Estructura primero, extrae después

### ScrapeGraphAI
- **Fortaleza:** IA + prompts naturales + búsqueda web
- **Debilidad:** Lento para volumen muy alto
- **Mejor caso:** Consultas específicas, datos variables
- **Filosofía:** Pregunta qué quieres, obtén resultados

---

**Documentación última actualización:** 2026-07-11  
**Herramientas disponibles en Claude Code:** ScrapeGraphAI ✅, Firecrawl ✅

---

# 📖 Guía de Uso: ScrapeGraphAI + Firecrawl

## Introducción

Esta guía te muestra **exactamente qué escribir** en Claude Code Chat para usar las herramientas de web scraping.

---

## 🎯 Tabla Rápida

| Necesidad | Herramienta | Comando |
|-----------|-------------|---------|
| Extraer datos de una página | ScrapeGraphAI | `Scrape [URL] y extrae...` |
| Buscar en Google/web | ScrapeGraphAI | `Busca "..." en la web` |
| Rastrear múltiples páginas | Firecrawl | `Usa Firecrawl para crawlear [URL]...` |
| Comparar datos de 2 sitios | ScrapeGraphAI | Dos comandos `Scrape` seguidos |

---

## 📋 ScrapeGraphAI - Ejemplos Listos para Copiar

### ✅ Ejemplo 1: GitHub Trending
```
Scrape https://github.com/trending?since=daily y dame los 5 repositorios más populares con descripción
```

**Qué obtiene:**
- Nombre del repositorio
- Descripción
- Lenguaje de programación
- Número de estrellas
- URL

---

### ✅ Ejemplo 2: Amazon - Buscar Laptops
```
Scrape https://amazon.es/s?k=laptop y extrae los 10 primeros laptops con nombre, precio y rating
```

**Qué obtiene:**
- Nombre del modelo
- Precio
- Rating/Estrellas
- Número de reviews
- URL del producto

---

### ✅ Ejemplo 3: Buscar en la Web
```
Busca "mejores VPN 2026" en la web y dame los 5 mejores resultados con descripción y precio
```

**Qué obtiene:**
- Top 5 resultados de búsqueda
- Descripción de cada VPN
- Precios si están disponibles
- Enlaces

---

### ✅ Ejemplo 4: E-commerce - Comparar Precios
```
Scrape https://amazon.es/s?k=iphone+16 y extrae los primeros 5 iPhones con nombre y precio
Scrape https://pccomponentes.com/s/iphone+16 y extrae los primeros 5 iPhones con nombre y precio
Ahora crea una tabla comparativa mostrando el más barato
```

**Qué obtiene:**
- Precio en Amazon
- Precio en PCComponentes
- Diferencia de precio
- Recomendación de compra

---

### ✅ Ejemplo 5: Wikipedia - Contenido
```
Scrape https://en.wikipedia.org/wiki/Artificial_intelligence y extrae el resumen principal, historia y aplicaciones modernas
```

**Qué obtiene:**
- Contenido estructurado
- Secciones principales
- Datos en formato claro

---

### ✅ Ejemplo 6: LinkedIn (si es accesible)
```
Scrape https://www.linkedin.com/feed y extrae los 10 posts principales con autor, contenido y likes
```

**Qué obtiene:**
- Nombre del autor
- Contenido del post
- Número de likes/comentarios

---

## 🕷️ Firecrawl - Ejemplos Listos para Copiar

### ✅ Ejemplo 1: Crawlear un Sitio Completo
```
Usa Firecrawl para crawlear https://miuraboard.com y extrae todos los productos disponibles con precios
```

**Qué obtiene:**
- Todas las páginas del sitio
- Lista completa de productos
- Estructura del sitio mapeada
- Enlaces internos

---

### ✅ Ejemplo 2: Wikipedia - Extracción Completa
```
Usa Firecrawl para scrapear https://en.wikipedia.org/wiki/Artificial_intelligence 
y extrae el contenido completo en Markdown con todos los enlaces
```

**Qué obtiene:**
- Texto completo de la página
- Todos los enlaces internos y externos
- Formato Markdown
- Estructura preservada

---

### ✅ Ejemplo 3: Mapeo de Estructura
```
Usa Firecrawl para crawlear https://github.com/trending 
y dame la estructura completa con todos los enlaces encontrados
```

**Qué obtiene:**
- Todos los enlaces de la página
- Estructura HTML mapeada
- Número total de enlaces
- Categorías de enlaces

---

### ✅ Ejemplo 4: E-commerce Completo
```
Usa Firecrawl para crawlear https://example-store.com/products 
y extrae una lista de TODOS los productos con nombre, precio y enlace
```

**Qué obtiene:**
- Todos los productos (no solo primeros 10)
- Precios
- Enlaces directos
- Estructura completa

---

### ✅ Ejemplo 5: Blog - Extracción de Artículos
```
Usa Firecrawl para scrapear https://example-blog.com 
y extrae todos los artículos con título, fecha y enlace
```

**Qué obtiene:**
- Listado completo de artículos
- Títulos
- Fechas de publicación
- Enlaces

---

## 🔄 Flujos Combinados (ScrapeGraphAI + Firecrawl)

### ✅ Flujo 1: Investigación Completa
```
Paso 1: Busca "mejores hosting 2026" en la web
Paso 2: Scrape https://site1.com y extrae planes y precios
Paso 3: Scrape https://site2.com y extrae planes y precios
Paso 4: Crea tabla comparativa de los 3 mejores
```

---

### ✅ Flujo 2: Análisis de Competencia
```
Paso 1: Usa Firecrawl para crawlear https://competidor1.com
Paso 2: Usa Firecrawl para crawlear https://competidor2.com
Paso 3: Scrape ambos y extrae: productos, precios, promociones
Paso 4: Dame un análisis de fortalezas y debilidades
```

---

### ✅ Flujo 3: Monitoreo de Precios
```
Paso 1: Scrape https://amazon.es/s?k=producto y extrae precios
Paso 2: Scrape https://other-store.com y extrae precios
Paso 3: Scrape https://another-site.com y extrae precios
Paso 4: Crea gráfico de precios por tienda
```

---

## 💡 Consejos Prácticos

### Para obtener mejores resultados:

#### ✅ SÍ - Sé específico:
```
Scrape https://amazon.es/s?k=laptop y extrae nombre, precio y rating de los primeros 10 resultados
```

#### ❌ NO - Vago:
```
Scrape Amazon y dame laptops
```

---

#### ✅ SÍ - Especifica formato:
```
Scrape [URL] y extrae en formato tabla CSV
```

#### ❌ NO - Sin formato:
```
Scrape [URL] y dame todo
```

---

#### ✅ SÍ - Campos concretos:
```
Extrae: nombre, precio, descripción breve, enlace directo
```

#### ❌ NO - Demasiado genérico:
```
Extrae toda la información
```

---

## 🎮 Casos de Uso Reales

### Caso 1: Buscar Laptop barata
```
Scrape https://amazon.es/s?k=laptop y extrae nombre, precio de los 20 primeros
Scrape https://pccomponentes.com/s/laptop y extrae nombre, precio de los 20 primeros
Ahora dame los 5 más baratos en total
```

---

### Caso 2: Análisis de GitHub
```
Scrape https://github.com/trending?since=daily y extrae top 10 con descripción
Busca en la web qué son estos proyectos
Dame un resumen de tendencias en desarrollo
```

---

### Caso 3: Auditoría SEO
```
Usa Firecrawl para crawlear https://example.com
Extrae todos los títulos, meta descriptions y URLs
Dame un reporte de SEO básico
```

---

### Caso 4: Comparativa de Precios
```
Scrape https://amazon.es/s?k=iphone+16 y extrae precio
Scrape https://fnac.es/s/iphone+16 y extrae precio
Scrape https://mediamarkt.es/s/iphone+16 y extrae precio
Dame tabla con el más barato
```

---

## 🚀 COPIA Y PEGA - Ejemplos Probados

### Opción 1 (Más fácil):
```
Scrape https://github.com/trending?since=daily y dame los 10 repositorios más populares
```

### Opción 2 (Con búsqueda):
```
Busca "best AI tools 2026" en la web
```

### Opción 3 (Comparación):
```
Scrape https://amazon.es/s?k=laptop y extrae precio
Scrape https://pccomponentes.com/s/laptop y extrae precio
Compara y dame el más barato
```

### Opción 4 (Firecrawl masivo):
```
Usa Firecrawl para scrapear https://miuraboard.com y extrae todos los productos
```

---

## ❓ Preguntas Frecuentes

### P: ¿Cuál debo usar?
**R:** 
- **ScrapeGraphAI**: Para 1-10 páginas, búsquedas específicas
- **Firecrawl**: Para 10+ páginas, crawling completo del sitio

### P: ¿Funciona con cualquier sitio?
**R:** Sí, pero algunos sitios pueden bloquear. Intenta primero y si falla, intenta otro sitio.

### P: ¿Puedo combinarlas?
**R:** Sí, puedes usarlas en la misma conversación. Ej: Busca + Scrape + Scrape.

### P: ¿Cuánto tarda?
**R:** ScrapeGraphAI: 2-5 segundos. Firecrawl: 10-30 segundos (depende del sitio).

### P: ¿Hay límites?
**R:** Sí, hay límites de API. Si lo usas mucho, considera obtener una API key propia.

---

## 📝 Formato Recomendado

**SIEMPRE usa este patrón:**
```
[Herramienta] [URL] y extrae:
- Campo 1
- Campo 2
- Campo 3
En formato [CSV/Tabla/JSON]
```

**Ejemplo:**
```
Scrape https://example.com/products y extrae:
- Nombre
- Precio
- URL
En formato tabla
```

---

## ✅ Resumen Final

| Paso | Qué escribir |
|------|-------------|
| 1 | Escribe el comando exactamente como aparece arriba |
| 2 | Presiona Enter |
| 3 | Espera la respuesta (2-30 segundos) |
| 4 | Recibe datos extraídos |
| 5 | Pide análisis, formato o comparación si necesitas |

**¡Listo!** Ahora tienes todo lo que necesitas. 🚀

---

**Última actualización:** 2026-07-11  
**Herramientas disponibles:** ✅ ScrapeGraphAI + ✅ Firecrawl
