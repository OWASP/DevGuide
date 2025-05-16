Los datos sensibles como contraseñas, números de tarjetas de crédito, registros médicos,
información personal y secretos comerciales requieren protección adicional, particularmente si esos datos están
sujetos a leyes de privacidad (Reglamento General de Protección de Datos de la UE, GDPR),
reglas de protección de datos financieros como el
Estándar de Seguridad de Datos para la Industria de Tarjetas de Pago (PCI DSS) u otras regulaciones.

Consulte el control proactivo [C2: Usar la Criptografía de manera adecuada][control2]
y sus [hojas de referencia][csproactive-c8]
para obtener más contexto del proyecto OWASP Top 10 Controles Proactivos,
y utilice la lista a continuación como sugerencias para una lista de verificación adaptada para el proyecto individual.

#### 1. Protección de datos

1. Clasificar los datos según el nivel de sensibilidad
2. Implementar controles de acceso apropiados para datos sensibles
3. Cifrar datos en tránsito
4. Asegurar que los canales de comunicación seguros estén configurados correctamente
5. Evitar almacenar datos sensibles cuando sea posible
6. Asegurar que los datos sensibles en reposo estén protegidos criptográficamente para evitar divulgación
    y modificación no autorizada
7. Eliminar datos sensibles cuando ya no sean necesarios
8. Almacenar secretos a nivel de aplicación en una bóveda de secretos
9. Verificar que los secretos no estén almacenados en código, archivos de configuración o variables de entorno
10. Implementar el privilegio mínimo, restringiendo el acceso a funcionalidades, datos e información del sistema
11. Proteger todas las copias en caché o temporales de datos sensibles contra acceso no autorizado
12. Eliminar esas copias temporales de datos sensibles tan pronto como ya no sean necesarias

#### 2. Gestión de memoria

1. Inicializar explícitamente todas las variables y almacenes de datos
2. Verificar que los búferes sean tan grandes como se especifica
3. Comprobar los límites del búfer si se llama a la función en un bucle y proteger contra desbordamientos
4. Cerrar específicamente los recursos, no depender del recolector de basura
5. Usar pilas no ejecutables cuando estén disponibles
6. Liberar correctamente la memoria asignada al completar las funciones y en todos los puntos de salida
7. Sobrescribir cualquier información sensible almacenada en la memoria asignada en todos los puntos de salida de la función
8. Proteger las variables y recursos compartidos contra el acceso concurrente inapropiado

#### Referencias

* [Hoja de Referencia: Almacenamiento Criptográfico][cscs] de OWASP
* [Hoja de Referencia: Gestión de Secretos][cssm] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060208].

La Guía para Desarrolladores OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue060208] o [edítelo en GitHub][edit060208].

[csproactive-c8]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c8-protect-data-everywhere
[control2]: https://top10proactive.owasp.org/the-top-10/c2-crypto/
[cscs]: https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet
[cssm]: https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet
[edit060208]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/08-protect-data.md
[en060208]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/08-protect-data/
[issue060208]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/08-protect-data
[proactive10]: https://top10proactive.owasp.org/
