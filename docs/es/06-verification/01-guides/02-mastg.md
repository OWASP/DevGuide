![Logo MAS](../../../assets/images/logos/mas.png "Estándar de Verificación MAS de OWASP"){ align=right width=180 }

El [Estándar de Verificación MAS][masvs] (MASVS) explica los procesos, técnicas
y herramientas utilizadas para las pruebas de seguridad de una aplicación móvil.

El proyecto [MAS][mas] de OWASP proporciona la [Guía de Pruebas de Seguridad de Aplicaciones Móviles][mastg] (MASTG)
que describe los procesos técnicos que pueden utilizarse para la verificación de los controles de aplicaciones móviles.

#### ¿Qué es MASTG?

La [Guía de Pruebas de Seguridad de Aplicaciones Móviles][mastg] de OWASP es un manual completo
para pruebas de seguridad y ingeniería inversa de aplicaciones móviles.
Describe los procesos técnicos utilizados para verificar los controles enumerados en el OWASP MASVS.

La guía MASTG proporciona varios recursos para probar los controles:

* Secciones que detallan los conceptos y teoría detrás de las pruebas de las plataformas Android e iOS
* Listas de [pruebas][mastgtests] para cada sección del [MASVS][masvs]
* Descripciones de [técnicas][mastgtechs] para Android o iOS utilizadas durante las pruebas
* Listas de [herramientas][mastgtools] genéricas y también específicas para Android o iOS
* [Aplicaciones][mastgapps] de referencia que pueden utilizarse como material educativo

#### ¿Por qué usar MASTG?

El OWASP MASVS es el estándar de la industria para [seguridad de aplicaciones móviles][csmas],
y proporciona una lista de controles de seguridad que se esperan en una aplicación móvil.
Si la aplicación no implementa estos controles correctamente, podría ser vulnerable;
la guía MASTG prueba que la aplicación tiene los controles enumerados en el MASVS.

#### Cómo utilizar MASTG

La serie OWASP Spotlight proporciona una descripción general del uso de la MASTG:
'Proyecto 13 - [Guía de Pruebas de Seguridad Móvil de OWASP (MSTG)][spotlight13]'.

El proyecto MASTG contiene una gran cantidad de recursos que pueden utilizarse durante la verificación
y pruebas de aplicaciones móviles; seleccione los recursos que sean aplicables a la aplicación específica.

* Consulte la sección de MASTG sobre los conceptos y teoría para asegurar una buena comprensión del proceso de prueba
* Seleccione las [pruebas MASTG][mastgtests] que sean aplicables a la aplicación y su plataforma de Sistema Operativo
* Utilice la sección sobre [técnicas MASTG][mastgtechs] para ejecutar correctamente las pruebas seleccionadas
* Familiarícese con la gama de [herramientas MASTG][mastgtools] disponibles y seleccione las que necesita
* Utilice las [Listas de Verificación MAS][masc] para proporcionar evidencia de cumplimiento

#### Referencias

* Proyecto OWASP [Seguridad de Aplicaciones Móviles][masproject] (MAS)
* [Guía de Pruebas MAS][mastg] (MASTG) de OWASP
* [Listas de Verificación MAS][masc] de OWASP
* [Estándar de Verificación MAS][masvs] (MASVS) de OWASP
* Hoja de Referencia de OWASP para [Seguridad de Aplicaciones Móviles][csmas]

----

Traducción de versión [original en inglés][en080102].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambios,
[envíe un issue][issue080102] o [edite en GitHub][edit080102].

[csmas]: https://cheatsheetseries.owasp.org/cheatsheets/Mobile_Application_Security_Cheat_Sheet
[edit080102]: https://github.com/OWASP/DevGuide/blob/main/docs/es/06-verification/01-guides/02-mastg.md
[en080102]: https://devguide.owasp.org/en/06-verification/01-guides/02-mastg/
[issue080102]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2006-verification/01-guides/02-mastg
[mas]: https://mas.owasp.org/
[masproject]: https://owasp.org/www-project-mobile-app-security/
[masc]: https://mas.owasp.org/checklists/
[mastg]: https://mas.owasp.org/MASTG/
[mastgapps]: https://mas.owasp.org/MASTG/apps/
[mastgtests]: https://mas.owasp.org/MASTG/tests/
[mastgtechs]: https://mas.owasp.org/MASTG/techniques/
[mastgtools]: https://mas.owasp.org/MASTG/tools/
[masvs]: https://mas.owasp.org/MASVS/
[spotlight13]: https://youtu.be/b07OQd5KSrs
