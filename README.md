Proyecto 1 Limpieza y Transformación de Datos de GreenMart
Claudio Grondona Pérez


Breve descripción del proyecto.

Este proyecto consiste en una limpieza y normalización de datos para la empresa “Greenmart”.

Los datos constan de 11 columnas y 10400 filas. Estos datos necesitan ser filtrados para eliminar filas duplicadas, eliminar o arreglar inconsistencias con datos nulos, estructurar y hacer normativos algunos de los campos.

Los datos matemáticos han de ser consistentes, estructurados y en definitiva dejar unos datos listos para un análisis.


La limpieza de datos es una (si no la más) de las fases clave de cualquier análisis o preparación para machine learning.

En los datos provistos he detectado la presencia de valores nulos, registros duplicados, tipos de datos incorrectos y valores atípicos extremos que podían distorsionar la realidad de la tienda.

Procesos de limpieza y decisiones clave.

Vamos a dividir este apartado en tres subapartados, empezaremos por la gestión de duplicados:

Se han encontrado 367 filas totalmente duplicadas, esto en una empresa de venta tanto al público como al pormayor, puede ser posible. Sin embargo al carecer estos datos de un identificador de la compra (tal como un número de transacción o de ticket) o incluso la hora de la compra no se puede garantizar que sean copias legítimas. Esto hace que haya decidido borrarlos. teniendo en cuenta el bajo impacto que podría tener la desaparición de estos datos.

Pasamos ahora a hablar del tratamiento de nulos: 

En las columnas en las que tenemos texto (str)  hemos preservado las líneas con fallos al sustituirlas por un sencillo “desconocido”. Esto afecta a nombre y ciudad por ejemplo.

Esta decisión está basada en que creo que estos datos son útiles desde un punto de vista de ventas y financiero, lo cual deja en un segundo plano a el “quién” para centrarse en un “cuanto”.
En cuanto a los bloques financieros como gastos totales, se ha eliminado de forma sistemática un 7% de datos que tenían un patrón de errores sistémicos donde faltaban datos críticos.

Por último hablaremos de la estandarización:

Todos los campos con texto han sido normalizados en minúsculas, para poder así evitar espacios en blanco y diferentes versiones de las mismas palabras. Igualmente para el campo de fecha de compra se le ha dado formato de “datetime” lo cual podría facilitar en el futuro el trabajo con los datos pudiendo filtrar por días, mes o año.

Se hizo también un análisis de anomalías y una validación matemática de algunos campos.

Se eliminaron 14 registros que claramente eran algún tipo de error (ej. compras de 3200 euros en leche sin ningún dato del cliente).

Se tomó la decisión de mantener 96 compras “sospechosas” que tenían más de 100 unidades de algún artículo. Esta decisión se motivó en que podría ser una compra por parte de un mayorista ya que todos los datos eran, en principio, correctos.

Por último se confirmó que en el 100% de registros coincide el total gastado con las columnas de precio y cantidad.

 
Estado final y conclusiones.

En cuanto a las métricas, queda confirmado la ausencia total de valores nulos.

Por último, tras una brevísima reflexión del negocio y tras realizar un gráfico muy ilustrativo
podemos deducir que la venta de los productos “orgánicos” es el motor principal de ingresos, lo cual hace que tenga que prestar atención al cuidado de sus líneas de venta.

El apartado “snack” presenta una alta rentabilidad por unidad vendida, se sugiere colocarlo en lugares estratégicos como en línea de caja o en venta cruzada.

Por último “dairy” atrae volumen y genera menos ingresos, pero ese volumen que viene a por este producto es un potencial comprador de otros productos de la tienda. Se recomienda utilizar este reclamo para impulsar otras áreas.
