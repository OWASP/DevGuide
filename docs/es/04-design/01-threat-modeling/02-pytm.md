![Logo de pytm](../../../assets/images/logos/pytm.png "OWASP pytm"){ align=right width=180 }

El proyecto OWASP [pytm (Modelado de Amenazas Pythónico)][pytmproject] es un marco
para el modelado de amenazas y su automatización.
El objetivo de pytm es realizar el modelado de amenazas Shift-Left, lo que significa iniciar
el modelado ya en etapas tempranas del proyecto, haciendo que el modelado de amenazas sea más automatizado
y centrado en el desarrollador.

Pytm es un Proyecto de Producción de OWASP con una comunidad de colaboradores
que crean [versiones regulares][pytmreleases].

#### ¿Qué es pytm?

Pytm es una biblioteca Python que proporciona una forma programática de modelado de amenazas;
el modelo de aplicación en sí se define como un archivo fuente de python3 y sigue la sintaxis del programa Python.
Los hallazgos se incluyen en un informe de modelado de amenazas basado en plantillas.
El archivo de amenazas puede reutilizarse entre proyectos y permite la acumulación de una base de conocimiento.

Usando pytm, el modelo y las amenazas pueden ser programáticamente generados
como un diagrama de flujo de datos [dot][graphvizdot]
que se muestra utilizando [Graphviz][graphviz], una utilidad de software de visualización de gráficos de código abierto.
Alternativamente, el modelo y las amenazas pueden generarse como un archivo [PlantUML][plantuml] que luego puede mostrarse,
usando Java y el archivo `.jar` de PlantUML, como un diagrama de secuencia.

Si se requiere un documento de informe, un script de pytm puede generar el modelo,
las amenazas y los hallazgos como markdown.
Programas como [pandoc][pandoc] pueden tomar este archivo markdown despues
y proporcionar el documento en varios formatos como PDF, ePub o html.

La serie Spotlight de OWASP proporciona una visión general de pytm: 'Proyecto 6 - [OWASP pytm][spotlight06]'.

#### ¿Por qué usar pytm?

El equipo de desarrollo de pytm señala con razón que el modelado de amenazas tradicional a menudo llega demasiado tarde
en el proceso de desarrollo, y a veces puede no ocurrir en absoluto.
Además, crear flujos de datos manuales/diagramáticos e informes puede consumir muchísimo tiempo.
Estas son ciertamente observaciones válidas,
y por lo tanto pytm intenta que el modelado de amenazas "se desplace a la izquierda" en el ciclo de vida del desarrollo.

Muchas herramientas tradicionales de modelado de amenazas como OWASP Threat Dragon proporcionan
una forma gráfica de crear diagramas e introducir amenazas.
Estas aplicaciones almacenan los modelos como texto, por ejemplo JSON y YAML,
pero el método principal de entrada es a través de la aplicación.

Pytm es diferente - el método principal para crear y actualizar los modelos de amenazas es a través de código.
Este código fuente define completamente el modelo junto con sus hallazgos, amenazas y remediaciones.
Los diagramas e informes se consideran salidas del modelo; no las entradas al modelo.
Esto hace que pytm sea una herramienta poderosa para describir un sistema o aplicación,
y permite que el modelo se continúe construyendo con el tiempo.

Este enfoque en el modelo como código y salidas programáticas hace que Pytm
sea particularmente útil en entornos automatizados,
ayudando a que el modelo de amenazas se integre en el proceso de diseño desde el principio,
así como en sesiones de modelado de amenazas más tradicionales.

#### Cómo usar pytm

La mejor descripción de cómo usar pytm se encuentra en el capítulo 4 del libro
[Threat Modeling: a practical guide for development teams][TMchap4]
que está escrito por dos de los principales colaboradores del proyecto pytm.

Pytm está basado en código dentro de un entorno de programa, en lugar de ejecutarse como una aplicación única,
por lo que hay varios componentes que deben instalarse en la máquina de destino para permitir que pytm se ejecute.
Actualmente no funciona en Windows, solo en Linux o MacOS, por lo que si necesita ejecutar Windows, use una VM de Linux
o siga las instrucciones para crear un contenedor Docker.

Las siguientes herramientas y bibliotecas deben estar instaladas:

* Python 3.x
* Paquete [Graphviz][graphvizdot]
* Java, como OpenJDK 10 u 11 (solamente para el uso del diagrama de secuencia)
* El archivo JAR ejecutable de [PlantUML][plantumljar]
* Y por supuesto pytm: clone el [repositorio del proyecto pytm][pytmrepo]

Una vez instalado el entorno, navegue al directorio principal de su copia local del proyecto.

Siga [el ejemplo][pytmexample] proporcionado por el repositorio del proyecto pytm y ejecuta los scripts sugeridos
para generar el diagrama de flujo de datos, el diagrama de secuencia y el informe:

```text
mkdir -p tm
./tm.py --report docs/basic_template.md | pandoc -f markdown -t html > tm/report.html
./tm.py --dfd | dot -Tpng -o tm/dfd.png
./tm.py --seq | java -Djava.awt.headless=true -jar $PLANTUML_PATH -tpng -pipe > tm/seq.png
```

#### Referencias

* [Modelado de Amenazas Pythónico][pytmproject]  (pytm) de OWASP
* [Graphviz][graphviz]
* [pandoc][pandoc]
* [PlantUML][plantuml]
* Repositorio [pytm][pytmrepo]
* [Spotlight][spotlight06] sobre pytm
* [Threat Modeling: una guía práctica para equipos de desarrollo][TMchap4]

----

Traducción de versión [original en inglés][en060102].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue060102] o [edítelo en GitHub][edit060102].

[edit060102]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/01-threat-modeling/02-pytm.md
[graphviz]: https://graphviz.org/
[graphvizdot]: https://graphviz.org/download/
[en060102]: https://devguide.owasp.org/en/04-design/01-threat-modeling/02-pytm/
[issue060102]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/01-threat-modeling/02-pytm
[pandoc]: https://pandoc.org/installing.html
[plantuml]: https://plantuml.com/
[plantumljar]: https://plantuml.com/download
[pytmrepo]: https://github.com/OWASP/pytm/
[pytmproject]: https://owasp.org/www-project-pytm/
[pytmexample]: https://github.com/OWASP/pytm/blob/master/tm.py
[pytmreleases]: https://github.com/OWASP/pytm/releases
[spotlight06]: https://youtu.be/oTqkPaEbTnE
[TMchap4]: https://www.oreilly.com/library/view/threat-modeling/9781492056546/ch04.html
