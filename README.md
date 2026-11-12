# Cash Flow Pod Tracker

Dashboard de clientes, responsables y status del Cash Flow Pod. Son dos archivos: `index.html` (la página) y `data.json` (los datos). La página lee `data.json` cada vez que se abre, así que para actualizar algo solo se edita ese archivo.

## Publicarlo en GitHub Pages (una sola vez, 10 minutos)

1. En github.com, crear un repositorio nuevo, por ejemplo `cashflow-pod-tracker`.
2. Botón **Add file, Upload files**: subir `index.html` y `data.json` en la raíz del repositorio. Commit.
3. **Settings, Pages**: Source "Deploy from a branch", branch `main`, carpeta `/ (root)`. Save.
4. En uno o dos minutos GitHub muestra el link, por ejemplo `https://tgg-accounting.github.io/cashflow-pod-tracker/`.

Nota: GitHub Pages desde un repositorio privado necesita un plan pago (Pro, Team o Enterprise). Con un repositorio público el link y el contenido de `data.json` quedan visibles para cualquiera que tenga la URL, así que conviene no poner montos ni datos sensibles de clientes en las notas.

## Actualizar un status

1. En el repositorio, abrir `data.json` y tocar el lápiz (Edit).
2. Cambiar los campos del cliente y la fecha de `updated` arriba de todo.
3. **Commit changes**. El link se actualiza en uno o dos minutos.

Campos de cada cliente:

| Campo | Qué poner |
|---|---|
| `owner` | Miraluna, Walter, Jose o Sofi. Vacío `""` muestra "Sin asignar" |
| `stage` | Una de las etapas de la lista `stages`: En progreso, Draft enviado, Follow up, Meeting agendada, Testing, Implementado |
| `status` | Frase corta que se ve debajo del nombre |
| `nextAction` | Próxima acción, por ejemplo "Follow up" |
| `nextDate` | Fecha de la próxima acción en formato `AAAA-MM-DD`. Se marca en rojo si está vencida y en amarillo si es hoy |
| `notes` | Historial. Para sumar una nota, agregar `{ "date": "2026-11-13", "text": "..." }` dentro de la lista, separada por coma |

Si la página muestra "No se pudo leer data.json", casi siempre es una coma de más o de menos en el JSON. Se puede validar pegándolo en jsonlint.com.

## Agregar un cliente

Copiar el bloque de un cliente completo (desde `{` hasta `}`), pegarlo después del último, poner una coma entre los dos bloques y cambiar los datos.
