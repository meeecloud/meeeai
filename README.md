# API MeeeAI - MeeeCloud

> **Servidor API:** `http://87.106.100.210:6169/`
> **Discord:** `https://discord.gg/YVCtPQXSsS`
> **Última actualización:** 22 de abril de 2025

---

## 📌 Descripción General

La API de MeeeAI ofrece servicios de generación de texto, generación de imágenes y estadísticas de uso para clientes registrados. Cuenta con varios modelos optimizados para distintos usos, desde alta calidad hasta velocidad.

---

## 🔗 Rutas y Uso

### 1. Generación de texto — `/chat`

Permite generar texto mediante diferentes modelos de lenguaje.

#### Formato de uso:
```
/chat/(modelo)/(mensaje)
```

#### Modelos disponibles:
| Modelo | Descripción                    |
|--------|-------------------------------|
| `/a2`  | ⭐ Mejor calidad de texto.       |
| `/a1`  | 🥈 Balance entre calidad y velocidad. |
| `/a4`  | 🥉 Modelo rápido y ligero.        |
| `/a3`  | ⏳ Resultados más actualizados.   |

#### Ejemplo:
```
http://87.106.100.210:6169/chat/a2/Cuentame una historia
```

---

### 2. Generación de imágenes — `/img`

Genera imágenes según descripción y modelo seleccionado.

#### Formato de uso:
```
/img/(modelo)/(descripción_imagen)/(opciones...)
```

#### Modelos disponibles:
| Modelo | Descripción                |
|--------|---------------------------|
| `/e1`  | ⭐ Mejor calidad de imagen.  |
| `/e2`  | 🚀 Rápido, menor calidad.    |

#### Opciones adicionales:
- `/b` — Mejora la calidad de la imagen.
- `/ancho/alto` — Cambia la resolución en píxeles.

#### Ejemplo:
```
http://87.106.100.210:6169/img/e1/un gato espacial/b/1920/1080
```

---

### 3. Estadísticas de uso — `/stats`

Devuelve información del estado actual del cliente y límites de uso.

#### Formato de uso:
```
/stats
```

#### Ejemplo de respuesta JSON:
```json
{
  "Cliente": "0.0.0.0",
  "Límites": {
    "Rutas permitidas": ["/chat", "/img"],
    "Enfriamiento (segundos)": 15,
    "Expiración de licencia": "2025-12-31",
    "Por minuto": 20,
    "Total de solicitudes": 100
  },
  "Uso actual": {
    "Solicitudes este minuto": 2,
    "Solicitudes usadas": 14,
    "Última solicitud": "2025-04-22 02:19:05"
  }
}
```

---

## ⚠️ Reglas y límites de uso

- ⏱️ Enfriamiento: XX segundos entre solicitudes.
- 📅 Licencia válida hasta: "dia" de "mes" de "año".
- 🚦 Límite por minuto: XX solicitudes.
- 📊 Total permitido: XX solicitudes por cuenta.

---

## ✅ Recomendaciones

- Para mejores resultados en texto, utiliza `/chat/a2`.
- Para información actualizada, prueba con `/chat/a3`.
- Para imágenes de alta calidad, usa `/img/e1` con el modificador `/b`.
- Para imágenes rápidas pero menos detalladas, usa `/img/e2`.

---
