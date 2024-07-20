Que es esto?
- Este es un ejemplo de como se me ocurre podria verse una version simulada (y probablemenete muy sobresimplicada) de los datos y de como podria abordarse el modelo (tambien de manera muy basica). 
- Todo el codigo [synthetic.ipynb](https://github.com/pablo-marin-vicuna/Predict_Ingredients/blob/main/synthetic.ipynb) esta en Ingles salvo este README porque en general las librerias estan disponibles en Ingles y es mucho mas natural mantenerse en ese idioma.

Datos:
- Como no tengo acceso a los datos, primero genero datos sinteticos (simulados) en funcion de distribuciones de variables para generar variables demograficas (variables independientes) y luego niveles de ingredientes (variables dependientes, relacionadas con las demograficas). Genero 10 mil filas de datos sinteticos. Puse referencias de distribuciones al principio del codigo por si son de utilidad.
- Variables demograficas: edad (Normal), ingresos (LogNormal), genero (probabilidades por categoria), nivel educacional (probabilidades por categoria). Para cada una me invento parametros que se me ocurren podrian ser no tan irreales para simular. Los parametros especificos estan en el codigo. No buscan ser realistas, es solo para tener datos para poder demostrar un posible proceso posterior.
- Variables de ingredientes: genero 4 ingredientes, cuyas distribuciones son "afectadas" por las variables demograficas. No tengo idea de las relaciones asi que simplemente agregue alguna relacion cualquiera, distinta para cada ingrediente. Por ejemplo el primero lo relacione con edad, el segundo con genero, el tercero con nivel educacional y el cuarto con edad e ingreso. 


Modelo:
- Uso los datos sinteticos para calibrar un modelo sencillo de regresion lineal y otro algo mas 'sofisticado' que es un Random Forest para predecir los niveles de cada ingrediente
- El modelo es bueno en la medida que los datos tengan relaciones entre si. Por lo que los resultados estan directamente relacionados a como y cuanto yo defini relacionar las variables. Esto implica que NO importa mucho el resultado que obtenga porque soy yo mismo el generador de los datos.
- Evaluo los resultados con metricas generales de R^2, RMSE, MAPE y especificas de Correlacion, RMSE y MAPE por cada ingrediente 
- Exporto resultado a XLSX [model_predictions.xlsx](https://github.com/pablo-marin-vicuna/Predict_Ingredients/blob/main/model_predictions.xlsx) para que sea mas facil de inspeccionar