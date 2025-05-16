![Logo la lista de verificación MAS](../../assets/images/logos/mas.png "Lista de verificación MAS"){ align=right width=180 }

El proyecto insignia de OWASP [Seguridad de Aplicaciones Móviles][masproject] (MAS) proporciona
estándares de la industria para la seguridad de aplicaciones móviles.

El proyecto OWASP MAS proporciona el [Estándar de Verificación de Seguridad de Aplicaciones Móviles][masvs] (MASVS)
para aplicaciones móviles y una completa [Guía de Pruebas de Seguridad de Aplicaciones Móviles][mastg] (MASTG).

La [Lista de verificación de Seguridad de Aplicaciones Móviles][masc] contiene enlaces
a los casos de prueba MASTG para cada control MASVS.

#### ¿Qué es la Lista de verificación MAS?

La Lista de verificación MAS proporciona una lista que hace seguimiento de los casos de prueba MASTG
para un control MASVS determinado.
Esta Lista de verificación MAS está dividida en categorías que coinciden con las categorías MASVS:

* [MASVS-STORAGE](https://mas.owasp.org/checklists/MASVS-STORAGE/) almacenamiento de datos sensibles
* [MASVS-CRYPTO](https://mas.owasp.org/checklists/MASVS-CRYPTO/) mejores prácticas de criptografía
* [MASVS-AUTH](https://mas.owasp.org/checklists/MASVS-AUTH/) mecanismos de autenticación y autorización
* [MASVS-NETWORK](https://mas.owasp.org/checklists/MASVS-NETWORK/) comunicaciones de red
* [MASVS-PLATFORM](https://mas.owasp.org/checklists/MASVS-PLATFORM/) interacciones con la plataforma móvil
* [MASVS-CODE](https://mas.owasp.org/checklists/MASVS-CODE/) puntos de entrada de la plataforma
y datos junto con software de terceros
* [MASVS-RESILIENCE](https://mas.owasp.org/checklists/MASVS-RESILIENCE/) integridad y ejecución en una plataforma confiable
* [MASVS-PRIVACY](https://mas.owasp.org/checklists/MASVS-PRIVACY/) privacidad de usuarios, datos y recursos

Además de los enlaces web, hay una [hoja de cálculo descargable][masxls].

#### ¿Por qué usarla?

El OWASP MASVS es el estándar de la industria para [seguridad de aplicaciones móviles][csmas].
Si se está aplicando el MASTG a una aplicación móvil, la Lista de verificación MAS es una referencia útil
que también puede utilizarse para fines de cumplimiento.

#### Cómo utilizarla

La [versión en línea][masc] es útil para listar los controles MASVS y qué pruebas MASTG aplican.
Siga los enlaces para acceder a los controles y pruebas individuales.

La [descarga de la hoja de cálculo][masxls] permite registrar el estado de cada prueba,
con una hoja separada para cada categoría MASVS.
Este registro de resultados de pruebas puede utilizarse como evidencia para fines de cumplimiento.

#### Referencias

* Proyecto de Seguridad de Aplicaciones Móviles ([MAS][masproject])
* [Lista de verificación][masc] MAS
* Estándar de Verificación MAS ([MASVS][masvs])
* Guía de Pruebas MAS ([MASTG][mastg])
* Hoja de Referencia de OWASP sobre [Seguridad de Aplicaciones Móviles][csmas]

----

Traducción de versión [original en inglés][en0603].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue0603] o [edítelo en GitHub][edit0603].

[csmas]: https://cheatsheetseries.owasp.org/cheatsheets/Mobile_Application_Security_Cheat_Sheet
[edit0603]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/03-mas-checklist.md
[en0603]: https://devguide.owasp.org/en/04-design/03-mas-checklist/
[issue0603]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/03-mas-checklist
[masproject]: https://owasp.org/www-project-mobile-app-security/
[masxls]: https://github.com/OWASP/owasp-mastg/releases/latest/download/OWASP_MAS_Checklist.xlsx
[masc]: https://mas.owasp.org/checklists/
[mastg]: https://mas.owasp.org/MASTG/
[masvs]: https://mas.owasp.org/MASVS/
