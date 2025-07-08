# API MeeeAI - MeeeCloud

> - **Servidor API:** `http://87.106.100.210:6169/`
> - **Pagina Web:** `http://87.106.52.7:6246/`
> - **Discord:** `https://discord.gg/YVCtPQXSsS`
> - **Última actualización:** 17 de junio de 2025

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
| `/a5`  | 😏 Modelo mas irónico, directo y veraz.   |
| `/ab6`  | 🔓 Modelo sin censura (Premium).   |

#### Ejemplo:
```
http://87.106.100.210:6169/chat/a2/Cuentame una historia
http://87.106.100.210:6169/chat/a3/Que dia es hoy
http://87.106.100.210:6169/chat/a1/Cuentame un chiste
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
| `/ef3`  | 🎨 Calidad superior, lento (Premium).    |
| `/ef4`  | 🎯 Muy preciso y rapido (Proximamente...).    |

#### Opciones adicionales:
- `/b` — Mejora la calidad de la imagen.
- `/s=seed_id` — Sirve para modificar la semilla de imagen.
- `/ancho/alto` — Cambia la resolución en píxeles.

#### Opciones adicionales unicas del modelo "ef3":
- `/res=1,2,3` — Modificar la calidad de imagen, cuanto mas alto el numero, mayor calidad y costo.
- `/url=url_imagen_1,url_imagen_2` — Puedes poner tanto una unica url de imagen para modificar cambios en ella (/url=url_imagen_1), como mezclar dos imagenes en una, añadiendo dos url en vez de una, separadas por una "," como en el ejemplo.
- `/sinfondo` — Si añades este parametro, hace una imagen la cual no tiene fondo (background).

#### Ejemplos:
```
http://87.106.100.210:6169/img/e2/un gatito blanco
http://87.106.100.210:6169/img/e1/un gato espacial/b/1920/1080
http://87.106.100.210:6169/img/e1/un gato en el bosque/b/s=123456/1920/1080
```

#### Ejemplos del modelo "ef3":
```
http://87.106.100.210:6169/img/ef3/un gatito blanco/res=2
http://87.106.100.210:6169/img/ef3/un gato espacial/b/res=1/sinfondo
http://87.106.100.210:6169/img/ef3/un gato en el bosque/b/res=3/url=url_imagen_1
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
  "Cliente": "nombre_del_cliente",
  "Límites": {
    "Acceso ilimitado": true,
    "Enfriamiento (segundos)": 0,
    "Expiración de licencia": "2999-12-31",
    "Nivel de prioridad": 0,
    "Por día": 0,
    "Por hora": 0,
    "Por minuto": 0,
    "Retraso de respuesta": 0,
    "Rutas permitidas": [
      "/chat",
      "/img"
    ],
    "Total de solicitudes": 0
  },
  "Modelos disponibles": {
    "imagen": [
      "e1",
      "e2"
    ],
    "texto": [
      "a1",
      "a2",
      "a3",
      "a4",
      "a5"
    ]
  },
  "Tipo": "Perfil específico",
  "Uso actual": {
    "Histórico por día": {
      "2999-12-01": 30,
      "2999-12-05": 13,
      "2999-12-06": 3,
      "2999-12-07": 33,
      "2999-12-08": 27,
      "2999-12-09": 19,
      "2999-12-10": 5,
      "2999-12-11": 8
    },
    "Histórico por hora": {
      "2999-12-11T13": 1,
      "2999-12-11T14": 2,
      "2999-12-11T17": 5
    },
    "Solicitudes esta hora": 99,
    "Solicitudes este minuto": 9,
    "Solicitudes hoy": 599,
    "Solicitudes usadas": 999,
    "Última solicitud": "2999-12-30 23:59:59"
  }
}
```

---

## 🚪 Acceso a la API
- Acceso con IP: Se te dara acceso a tu panel con la IP de tu servidor y este contara con los limites acordados. Para consultar tus estadisticas, accederas a la ruta /stats
- Acceso por Dominio: Se te dara acceso a tu panel con el Dominio de tu servidor y este contara con los limites acordados. Para consultar tus estadisticas, accederas a la ruta /stats
- Acceso por Key: Se te dara acceso a tu panel por una Key unica y este contara con los limites acordados. Para consultar tus estadisticas, accederas a la ruta /panel/nombre_de_tu_key/contraseña (tanto la key, como la contraseña, se acordara a la hora de comprar el acceso)

---

## ⏳ Colas de la API

| Opción    | Activado (`true`)                          | Desactivado (`false`)                     |
|-----------|--------------------------------------------|--------------------------------------------|
| **nofree**  | ✅ Usa cola privada (no comparte con usuarios gratuitos)  | ❌ Usa cola global (espera con todos)       |
| **clouding**| 🚀 Ignora TODAS las colas (máxima prioridad)             | ⏳ Usa cola global (espera con todos)             |

### Explicación rápida:
- **`nofree`**: Para usuarios premium (evita colas compartidas).   
- **`clouding`**: Máximo privilegio (sin colas, sin límites).  

### Combinaciones útiles:
1. `clouding: true` → **VIP** (nada de esperas).   
3. `nofree: false` → Usuario gratuito (cola global + cooldown).  

> ℹ️ **Nota:** `clouding` anula todas las demás reglas de colas.

---

# Niveles de Prioridad de la API: Cloudy 1-4

La API ahora incluye un sistema de niveles de **Cloudy 1-4**, diseñado para adaptar el acceso según la importancia y carga de tu proyecto. Cada nivel define cuántas solicitudes simultáneas puedes realizar antes de que tus peticiones sean encoladas.

## Tabla de Niveles Cloudy

| Nivel     | Descripción                                                                 | Solicitudes Simultáneas Permitidas |
|-----------|------------------------------------------------------------------------------|------------------------------------|
| **Cloudy 1** | Tendrás tu propia cola dedicada, pero no puedes ejecutar múltiples solicitudes al mismo tiempo. | 1                                  |
| **Cloudy 2** | Puedes realizar hasta 2 solicitudes al mismo tiempo.                     | 2                                  |
| **Cloudy 3** | Puedes realizar hasta 3 solicitudes al mismo tiempo.                     | 3                                  |
| **Cloudy 4** | Acceso completo: puedes realizar solicitudes ilimitadas simultáneamente. | Ilimitadas                         |

## Importante

- Si tu número de solicitudes simultáneas excede el límite permitido por tu nivel, **las solicitudes adicionales se colocarán en la cola normal compartida**, lo cual puede aumentar el tiempo de respuesta.
- El objetivo de este sistema es asegurar un acceso justo a los recursos según la carga y criticidad de cada proyecto.

## Ejemplo

Si estás en **Cloudy 2** e intentas hacer 4 solicitudes simultáneas:
- Las primeras 2 se procesarán de inmediato.
- Las otras 2 se colocarán en la cola normal y esperarán a que se libere capacidad.

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

## ❓ Dudas

- Si algun modelo tarda mucho en contestar es porque la API puede estar colapsada, esto suele resolverse solo en un tiempo.
- La web en la que puedes probar la API es http://87.106.52.7:6246/ y el token de acceso aparece en el canal de discord.
- Puedes acceder a la API tanto por acceso de IP, Dominio o KEY, pidiendo acceso a nuestros moderadores.
- En caso de que te encuentres con limites en tu cuenta, siempre podras decirselo al equipo MeeeCloud creando un #ticket en discord y nosotros decidiremos aumentarte el limite actual con el que cuentas.
- El unico modelo de generacion de imagenes que permite NSFW es el "e2".
- Las solicitudes de /chat pueden demorar entre 2-30s dependiendo de la complejidad de la respuesta.
- Las solicitudes de /img pueden demorar entre 5-15s en los modelos e1 y e2. El modelo ef3 suele durar entre 30-80s dependiendo de la complejidad de la imagen de respuesta.
- El modelo "ef3" no lee la resolucion como tal poniendo /1920/1080. Si necesitas modificar la resolucion de la imagen, deberas especificarlo en el prompt (Ej: Imagen horizontal de un gato) o (Ej: Imagen 16:9 de un gatito blanco)

---
