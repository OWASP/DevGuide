La validación de entradas es una colección de técnicas que aseguran que solo los datos con formato adecuado
puedan ingresar a una aplicación de software o componente del sistema.

Es vital que se realice la validación de entradas para proporcionar el punto de partida para una aplicación
o sistema seguro.
Sin validación de entradas, la aplicación/sistema de software seguirá siendo vulnerable a ataques nuevos y variados.

Consulte el control proactivo [C3: Validar Todas las Entradas y Manejar Excepciones][control3]
y sus [hojas de referencia][csproactive-c5]
para más contexto del proyecto Top 10 Controles Proactivos de OWASP,
y use la lista a continuación como sugerencias para una lista de verificación adaptada al proyecto individual.

#### 1. Validez sintáctica y semántica

1. Identificar todas las fuentes de datos y clasificarlas en confiables y no confiables
2. Validar todos los datos de entrada de fuentes no confiables, como datos proporcionados por el cliente
3. Codificar la entrada a un conjunto de caracteres común antes de validar
4. Especificar conjuntos de caracteres, como UTF-8, para todas las fuentes de entrada
5. Si el sistema admite conjuntos de caracteres extendidos UTF-8, validar después de completar la decodificación UTF-8
6. Verificar que los valores de encabezado del protocolo en solicitudes y respuestas contengan solo caracteres ASCII
7. Validar datos de redirecciones
8. Validar el rango de datos y también la longitud de datos
9. Utilizar la canonicalización para tratar con ataques de ofuscación
10. Todos los fallos de validación deben resultar en el rechazo de la entrada

#### 2. Bibliotecas y frameworks

1. Realizar toda la validación de entrada en un sistema confiable [^SCP1]
2. Usar una biblioteca o framework de validación de entrada centralizado para toda la aplicación
3. Si la rutina de validación estándar no puede hacerse cargo de algunas entradas, use verificaciones discretas adicionales
4. Si cualquier entrada potencialmente peligrosa _debe_ permitirse, implemente controles adicionales
5. Validar para los tipos de datos esperados utilizando una lista de permitidos en lugar de una lista de denegados

#### 3. Validar datos serializados

1. Implementar verificaciones de integridad o cifrado de los objetos serializados
    para prevenir la creación de objetos hostiles o la manipulación de datos
2. Aplicar restricciones estrictas de tipo durante la deserialización antes de la creación de objetos;
    típicamente se espera un conjunto definible de clases
3. Aislar las funciones que hacen deserialización para que se ejecuten en entornos de muy bajo privilegio,
    como contenedores temporales
4. Registrar excepciones y fallos de deserialización de seguridad
5. Restringir o monitorear la conectividad de red entrante y saliente de contenedores o servidores que deserializan
6. Monitorear la deserialización, por ejemplo, alertando si un agente de usuario deserializa constantemente

#### Referencias

* [Hoja de Referencia: Validación de Entrada][ivcs] de OWASP
* [Proyecto Java HTML Sanitizer][sanitizer] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060205].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiar,
entonces [cree un issue][issue060205] o [edítelo en GitHub][edit060205].

[^SCP1]: Lista de verificación de prácticas de codificación segura

[csproactive-c5]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c5-validate-all-inputs
[control3]: https://top10proactive.owasp.org/the-top-10/c3-validate-input-and-handle-exceptions/
[ivcs]: https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet
[edit060205]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/05-validate-inputs.md
[en060205]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/05-validate-inputs/
[issue060205]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/05-validate-inputs
[proactive10]: https://top10proactive.owasp.org
[sanitizer]: https://www.owasp.org/index.php/OWASP_Java_HTML_Sanitizer
