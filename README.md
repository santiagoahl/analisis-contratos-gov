<h1 align="center">
  <br>
  <a href="https://www.contratos.gov.co/consultas/inicioConsulta.do"><img src="https://www.creg.gov.co/sites/default/files/files_upload/contratacionpublica.png" alt="SECOP" width="300"></a>
  <br>
Análisis de contratos gubernamentales en Colombia
  <br>
</h1>

<h4 align="center">Aprendizaje automático para predicción de valor de contratos, agrupamiento de palabras clave y detección de anomalías. 
</h4>

<p align="center">
   <a href='https://github.com/shivamkapasia0' target="_blank"><img alt='scikit-learn' src='https://img.shields.io/badge/scikit-learn-100000?style=for-the-badge&logo=scikit-learn&logoColor=FFFFFF&labelColor=FF6A00&color=1882EA'/></a> <a href='https://pypi.org/project/wordcloud/' target="_blank"><img alt='wordcloud' src='https://img.shields.io/badge/Word-Cloud-100000?style=for-the-badge&logo=wordcloud&logoColor=white&labelColor=9CFFD2&color=E9FF80'/></a> <a href='https://www.nltk.org/' target="_blank"><img alt='nltk' src='https://img.shields.io/badge/Nltk-100000?style=for-the-badge&logo=nltk&logoColor=white&labelColor=0C249D&color=0C249D'/></a> <a href='https://radimrehurek.com/gensim/' target="_blank"><img alt='gensim' src='https://img.shields.io/badge/gensim-100000?style=for-the-badge&logo=gensim&logoColor=white&labelColor=0C249D&color=00BBD4'/></a> <a href='https://pandas.pydata.org/' target="_blank"><img alt='pandas' src='https://img.shields.io/badge/pandas-100000?style=for-the-badge&logo=pandas&logoColor=2D0090&labelColor=9D7BEA&color=D2C0FA'/></a> 
</p>

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#credits">Credits</a> •
  <a href="#license">License</a> 
</p>

![screenshot](https://winter-anchovy-50e.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F0b33107d-3986-4b8c-92cd-4762a2bcc607%2Fimag.png?id=096b43d2-303f-433f-90e5-fb28af546e68&table=block&spaceId=12eea25e-0790-4a8f-aa1c-b60f93c02da2&width=1140&userId=&cache=v2)

## Características principales

Este proyecto de machine learning tiene como objetivo analizar a detalle la información desplegada por la página oficial de datos abiertos del gobierno de Colombia y del Sistema Electrónico para la Contratación Pública (SECOP), todo con la finalidad de encontrar posibles anomalías, agrupar texto clave del objetivo de los contratos y predecir los gastos. 
El conjunto de datos es tomado de [SECOP Integrado | Gastos Gubernamentales](https://www.datos.gov.co/Gastos-Gubernamentales/SECOP-Integrado/rpmr-utcd). A continuación mostramos las características clave del proyecto:


* El conjunto de datos consta de 1996395 contratos (filas) por 21 columnas. Las columnas constan de la siguiente información:
	 * Nivel Entidad
	 * Nombre de la Entidad
	 * NIT de la Entidad
	 * Estado del Proceso
	 * Modalidad de Contratación
	 * Objeto a Contratar
	 * Tipo de Contrato
	 * Fecha de Firma del Contrato
	 * ID Contrato
	 * ID Proceso
	 * Valor Contrato
	 * Nom Raz Social Contratista
	 * URL Contrato
	 * Departamento Entidad
	 * Municipio Entidad
	 * Objeto del Proceso
	 * Fecha Inicio Ejecucion
	 * Fecha Fin Ejecucion
	 * Tipo Contrato (Es una característica duplicada, pero existe)
	 * Origen
	 * Documento Proveedor

* Tras limpiar datos duplicados, no relevantes o mal insertados, redujimos el tamaño del conjunto de datos en un 85%.

* La predicción de gastos utiliza un modelo de regresón con bosques aleatorios, cuyo input es tomado gracias a `one-hot-encoding` de las siguientes características

	* Nombre de la Entidad	
	* Estado del Proceso	
	* Objeto a Contratar	
	* Municipio Entidad	
	* Tipo Contrato


* Usamos módulos de  **Scikit-Learn** como:
  - `sklearn.ensemble.RandomForestRegressor`: Predictor de valor de contrato.
  -  `sklearn.metrics.r2_score` : Métrica para evaluar el desempeño del predictor.
* También se usaron técnicas de procesamiento de lenguaje natural con **GenSim** y **NLTK**. Obteniendo palabras clave como
	 - mantenimiento
	 - prestacion
	 - municipio
	 - profesionales
	 - suministro

* Finalmente, tomamos los contratos que se salían del 95% de los datos asociados a una distribución normal. Obteniendo 55 contratos anómalos (No por ello producto de acciones fraudulentas):
![screenshot](https://winter-anchovy-50e.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fff46babf-1721-4bcf-85c3-c72aae4c75cf%2FUntitled.png?id=9ca482b0-7866-4d96-8bb8-28942f0310d5&table=block&spaceId=12eea25e-0790-4a8f-aa1c-b60f93c02da2&width=2000&userId=&cache=v2)

## ¿Cómo usar?

Para ejecutar de manera local este proyecto, siga estos pasos:

```bash
# Clone el repositorio
$ git clone https://github.com/santiagoahl/analisis-contratos-gov.git

# Entre a la carpeta del repositorio
$ cd analisis-contratos-gov

```

## Creditos
Este proyecto hace uso de las siguientes librerías y conjuntos de datos:

- [Pandas](https://pandas.pydata.org/)
- [Sci-kit Learn](https://scikit-learn.org/)
- [NLTK](https://www.nltk.org/)
- [GenSim](https://radimrehurek.com/gensim/)
- [Word Cloud](https://pypi.org/project/wordcloud/)
- [Dataset](https://www.datos.gov.co/Gastos-Gubernamentales/SECOP-Integrado/rpmr-utcd)


## Licencia

MIT

---

> Web Site [santiagoal.super.site](https://santiagoal.super.site/) &nbsp;&middot;&nbsp;
> GitHub [@santiagoahl](https://github.com/santiagoahl) &nbsp;&middot;&nbsp;
> Twitter [@sahumadaloz](https://twitter.com/sahumadaloz)
