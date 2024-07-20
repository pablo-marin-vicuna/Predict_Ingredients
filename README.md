Que es esto?
- Este es un ejemplo de como se me ocurre podria verse una version simulada (y probablemenete muy sobresimplicada) de los datos y de como podria abordarse el modelo (tambien de manera muy basica). 
- Todo el codigo esta en Ingles salvo este README porque en general las librerias estan disponibles en Ingles y es mucho mas natural mantenerse en ese idioma.

Datos:
- Como no tengo acceso a los datos, primero genero datos sinteticos (simulados) en funcion de distribuciones de variables para generar variables demograficas (variables independientes) y luego niveles de ingredientes (variables dependientes, relacionadas con las demograficas). Genero 10 mil filas de datos sinteticos.
- Variables demograficas: edad, ingresos, genero, nivel educacional. Para cada una me invento parametros que se me ocurren podrian ser no tan irreales para simular. 
- Variables de ingredientes: genero 4 ingredientes, cuyas distribuciones son "afectadas" por las variables demograficas. No tengo idea de las relaciones asi que simplemente agregue alguna relacion cualquiera, distinta para cada ingrediente

Modelo:
- Uso los datos sinteticos para calibrar un modelo sencillo de regresion lineal y otro algo mas 'sofisticado' que es un Random Forest para predecir los niveles de cada ingrediente
- Evaluo los resultados con metricas generales de R^2, RMSE, MAPE y especificas de Correlacion, RMSE y MAPE por cada ingrediente 
- Exporto resultado a XLSX para que sea mas facil de inspeccionar