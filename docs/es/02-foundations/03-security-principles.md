Esta sección es una introducción muy breve a algunos conceptos utilizados en el dominio de la seguridad del software,
ya que estos pueden no ser familiares para muchos desarrolladores de aplicaciones.
La [serie de Hojas de Referencia][csproject] de OWASP proporciona explicaciones más detalladas
de estos principios de seguridad, vea las lecturas adicionales al final de esta sección.

#### Descripción general

Hay varios conceptos y términos utilizados en el dominio de la seguridad que son fundamentales para la comprensión
y discusión de la seguridad de aplicaciones.
Los arquitectos de seguridad y los ingenieros de seguridad estarán familiarizados con estos términos,
y los equipos de desarrollo también necesitarán esta comprensión para implementar aplicaciones seguras.

#### Seguridad por Diseño

La seguridad no debería ser una ocurrencia de último minuto o un complemento. Al desarrollar sistemas,
se debe comenzar identificando los requisitos de seguridad relevantes y tratarlos como una parte integral
del proceso general y del diseño del sistema.
Comience estableciendo y adoptando principios y políticas relevantes como base para su diseño,
luego integre la seguridad en su ciclo de vida de desarrollo.
Tenga también en cuenta que el sistema que está construyendo también necesitará mantenimiento
y que los operadores del sistema necesitarán gestionarlo de manera segura e incluso apagarlo y eliminarlo.
Por lo tanto, comprométase con operaciones seguras desarrollando principios
y prácticas de "gestión operativa"[^1] seguras.

#### Seguridad por Defecto

Seguro por defecto significa que la configuración predeterminada es la más segura posible.
Esta no es necesariamente la configuración más fácil de usar. Evalúe cuáles deberían ser las configuraciones,
basándose tanto en el análisis de riesgos como en pruebas de usabilidad.
Como resultado, el significado preciso depende solamente de su decisión.
Sin embargo, configure el sistema para proporcionar solo la funcionalidad mínima
y para prohibir y/o restringir específicamente el uso de todas las demás funciones, puertos, protocolos y/o servicios.
También configure los valores predeterminados para que sean lo más restrictivos posible,
de acuerdo con las mejores prácticas, sin comprometer la "Aceptabilidad psicológica"
y la "Usabilidad y Manejabilidad" del sistema.

#### Sin garantía de seguridad

Uno de los principios más importantes de la seguridad del software es que ninguna aplicación o sistema
está 100% garantizado de ser seguro contra todos los ataques.
Esto puede parecer un punto de partida inusualmente pesimista, pero simplemente reconoce el mundo real;
dado suficiente tiempo y recursos, cualquier sistema puede ser puesto en peligro.
El objetivo de la seguridad del software no es '100% seguro', sino hacer que sea lo suficientemente difícil
y las recompensas lo suficientemente pequeñas para que los actores malintencionados desistan
y busquen en otro lugar sistemas para explotar.

#### Defensa en Profundidad

También conocida como defensa por capas, la [defensa en profundidad][did] es un principio de seguridad
donde la defensa contra ataques se proporciona mediante múltiples controles de seguridad.
El objetivo es que se eliminen o mitiguen los puntos únicos de compromiso completo mediante la incorporación de
una serie o múltiples capas de salvaguardas de seguridad y contramedidas de mitigación de riesgos.

Si una capa de defensa resulta inadecuada, entonces, si se implementan estrategias defensivas diversas,
otra capa de defensa puede prevenir una vulneración completa y si esa es eludida,
la siguiente capa puede bloquear la explotación.

#### Fallar de Forma Segura

Este es un principio de seguridad que tiene como objetivo mantener la confidencialidad, integridad y disponibilidad
cuando se detecta una condición de error. Estas condiciones de error pueden ser resultado de un ataque,
o pueden deberse a fallas de diseño o implementación; en cualquier caso,
el sistema/aplicaciones debe predeterminar un estado seguro en lugar de un estado inseguro.

Por ejemplo, a menos que se le dé acceso explícito a un objeto a una entidad,
se le debe negar el acceso a ese objeto por defecto.
Esto a menudo se describe como 'Valores Predeterminados a Prueba de Fallos' o 'Seguro por Defecto'.

En el contexto de la seguridad del software, el término 'fallo seguro' se usa comúnmente de manera intercambiable
con fallo a prueba de errores, que proviene de la terminología de seguridad física.
Fallar de forma segura también ayuda a la resiliencia del software en el sentido de que el sistema/aplicación
puede recuperarse rápidamente ante defectos de diseño o implementación.

#### Mínimo Privilegio

Un principio de seguridad en el que a una persona o proceso se le otorga solo
el nivel mínimo de derechos de acceso (privilegios) que sea necesario para que esa persona
o proceso complete una operación asignada.
Este derecho debe otorgarse solo por la cantidad mínima de tiempo necesaria para completar la operación.

Esto ayuda a limitar el daño cuando un sistema es comprometido al minimizar la capacidad de un atacante
para escalar privilegios tanto lateral como verticalmente.
Para aplicar este [principio de mínimo privilegio][elp],
se debe establecer una granularidad adecuada de privilegios y permisos.

#### Compartimentar

El principio de mínimo privilegio funciona mejor si los derechos de acceso no son un modelo de acceso "todo o nada".
En su lugar, compartimente el acceso a la información en base a la "necesidad de conocer" para realizar ciertas tareas.
El principio de compartimentación ayuda a minimizar el impacto de una brecha de seguridad en caso de
un intento de violación exitoso, pero debe usarse con moderación para evitar que el sistema se vuelva inmanejable.
Por lo tanto, siga también el principio de "Economía de Mecanismo".

#### Separación de Deberes

También conocida como [separación de privilegios][sop], la separación de deberes es un principio de seguridad
que requiere que la finalización exitosa de una sola tarea dependa de dos o más condiciones que son insuficientes,
individualmente por sí mismas, para completar la tarea.

Hay muchas aplicaciones para este principio, por ejemplo, limitar el daño que un empleado molesto
o malintencionado puede hacer, o limitando la escalación de privilegios.

#### Economía de Mecanismo

También conocido como 'mantenlo simple', si hay múltiples implementaciones,
se debe elegir la implementación más simple y fácil de entender.

La probabilidad de vulnerabilidades aumenta con la complejidad del diseño arquitectónico del software y el código,
y aumenta aún más si es difícil seguir o revisar el código.
La superficie de ataque del software se reduce manteniendo el diseño del software
y los detalles de implementación simples y comprensibles.

#### Mediación Completa

Un principio de seguridad que asegura que la autoridad no sea eludida en solicitudes consecutivas de un objeto
por un sujeto, verificando la autorización (derechos y privilegios) en cada solicitud del objeto.

En otras palabras, las solicitudes de acceso de un sujeto para un objeto son completamente mediadas cada vez,
de modo que todos los accesos a los objetos deben ser verificados para asegurar que están permitidos.

#### Diseño Abierto

El principio de seguridad de diseño abierto establece que los detalles de implementación del diseño deben ser
independientes del diseño en sí,
permitiendo que el diseño permanezca abierto mientras que la implementación puede mantenerse en secreto.
Esto contrasta con la seguridad por oscuridad, donde la seguridad del software depende de la oscuridad del diseño en sí.

Cuando la arquitectura del software utiliza el concepto de diseño abierto,
la revisión del diseño en sí no resultará en perjuicio de los medios de defensa del software.

#### Mecanismo menos Común

El principio de seguridad de los mecanismos menos comunes prohíbe compartir mecanismos que son comunes
a más de un usuario o proceso si los usuarios o procesos están en diferentes niveles de privilegio.
Esto es importante cuando se defiende contra la escalación de privilegios.

#### Aceptabilidad Psicológica

Un principio de seguridad que tiene como objetivo maximizar el uso y la adopción de la funcionalidad de seguridad
en el software asegurando que la funcionalidad de seguridad sea fácil de usar
y al mismo tiempo transparente para el usuario.
La facilidad de uso y la transparencia son requisitos esenciales para que este principio de seguridad sea efectivo.

Los controles de seguridad no deberían hacer que el recurso sea significativamente más difícil de acceder
que si el control de seguridad no estuviera presente.
Si un control de seguridad proporciona demasiada fricción para los usuarios,
entonces pueden buscar formas de eliminar el control y "mantener las puertas abiertas".

#### Usabilidad y Gestionabilidad

Es un principio relacionado con la aceptabilidad psicológica,
pero va más allá de la mera aceptabilidad psicológica percibida para incluir también el diseño,
implementación y operación de los controles de seguridad.
La configuración, administración e integración de los componentes de seguridad
no debe ser excesivamente compleja u oscura.
Por lo tanto, utilice siempre estándares abiertos para la portabilidad e interoperabilidad,
use un lenguaje común en el desarrollo de requisitos de seguridad,
diseñe la seguridad para permitir la adopción regular de nueva tecnología,
asegure que exista un proceso de actualización seguro y lógico, automatice las actividades de gestión de seguridad
y esfuércese por proporcionar la facilidad de uso operativa.

#### Asegurar el Eslabón más Débil

Este principio de seguridad establece que la resiliencia de su software contra intentos de hackers dependerá
en gran medida de la protección de sus componentes más débiles, ya sea el código, el servicio o una interfaz.
Por lo tanto, identificar el componente más débil y abordar el riesgo más grave primero,
hasta alcanzar un nivel aceptable de riesgo, se considera una buena práctica de seguridad.

#### Aprovechamiento de Componentes Existentes

Este es un principio de seguridad que se enfoca en asegurar que la superficie de ataque no aumente
y que no se introduzcan nuevas vulnerabilidades mediante el fomento de la reutilización de
componentes de software existentes, código y funcionalidad.

Es más probable que los componentes existentes hayan sido probados y testeados, y por lo tanto sean más seguros,
y también deberían tener parches de seguridad disponibles.
Además, los componentes desarrollados dentro de la comunidad de código abierto tienen el beneficio adicional
de 'muchos ojos' y por lo tanto es probable que sean aún más seguros.

#### Referencias

* Serie de Hojas de Referencia de OWASP
  * [Hoja de Referencia de Autenticación][csauthn]
  * [Hoja de Referencia de Autorización][csauthz]
  * [Hoja de Referencia de Diseño de Producto Seguro][spdcs]
* Top 10 Controles Proactivos de OWASP
  * [C5: Configuraciones Seguras por Defecto](https://top10proactive.owasp.org/the-top-10/c5-secure-by-default/)
* Otros
  * [Compartmentalization (information security)](https://en.wikipedia.org/wiki/Compartmentalization_(information_security)),
(Wikipedia)
  * [Funcionalidad Mínima](https://csf.tools/reference/nist-sp-800-53/r5/cm/cm-7/), (NIST)
  * [Seguridad por Diseño](https://pubs.opengroup.org/security/o-esa/#_Toc291061712), (Open Group)
  * [Usabilidad y Manejabilidad](https://pubs.opengroup.org/security/o-esa/#_Toc291061714), (Open Group)

----

Traducción de versión [original en inglés][en0403].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0403] o [edítelo en GitHub][edit0403].

[^1]: [Gestión Operativa](https://owaspsamm.org/model/operations/operational-management/), (SAMM)

[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[csproject]: https://owasp.org/www-project-cheat-sheets/
[did]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet.html#2-the-principle-of-defense-in-depth
[edit0403]: https://github.com/OWASP/DevGuide/blob/main/docs/es/02-foundations/03-security-principles.md
[elp]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html#enforce-least-privileges
[en0403]: https://devguide.owasp.org/en/02-foundations/03-security-principles/
[issue0403]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/03-security-principles

[sop]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet.html#1-the-principle-of-least-privilege-and-separation-of-duties
[spdcs]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet
