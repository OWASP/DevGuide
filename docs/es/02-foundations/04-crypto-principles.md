La criptografía es fundamental para la Confidencialidad e Integridad de las aplicaciones y sistemas.
La serie de [Hojas de Referencia][csproject] de OWASP describe el uso de la criptografía y algunas de ellas están
listadas en la lectura adicional al final de esta sección.

#### Descripción general

Esta sección proporciona una breve introducción a la criptografía (a menudo simplemente referida como "crypto")
y los términos utilizados.
La criptografía es un tema amplio y puede volverse muy matemático,
pero afortunadamente para la mayoría de los equipos de desarrollo,
una comprensión general de los conceptos es suficiente.
Esta comprensión general, con la guía de arquitectos de seguridad, debería permitir la implementación
de criptografía por parte del equipo de desarrollo para la aplicación o sistema.

#### Usos de la criptografía

Aunque la criptografía estaba inicialmente restringida principalmente al ámbito militar y académico,
se ha vuelto omnipresente en la seguridad de las aplicaciones de software.
Los usos cotidianos comunes de la criptografía incluyen teléfonos móviles, contraseñas,
VPNs SSL, tarjetas inteligentes y DVDs.
La criptografía ha invadido la vida cotidiana y es muy utilizada por muchas aplicaciones web.

La criptografía es uno de los temas más avanzados de la seguridad de la información,
y uno cuya comprensión requiere más formación y experiencia.
Es difícil de implementar correctamente porque hay muchos enfoques para la encriptación,
cada uno con ventajas y desventajas que deben ser entendidas a fondo por los arquitectos de soluciones.

La implementación correcta y precisa de la criptografía es extremadamente crítica para su eficacia.
Un pequeño error en la configuración o codificación resultará en la eliminación de la mayoría de la protección
y hará que la implementación criptográfica sea inútil.

Se requiere una buena comprensión de la criptografía para poder discernir entre productos sólidos y soluciones engañosas.
La complejidad inherente de la criptografía hace que sea fácil caer en afirmaciones fantásticas
de los proveedores sobre su producto.
Típicamente, estas son "un avance en criptografía" o "irrompible" o proporcionan seguridad "de grado militar".
Si un proveedor dice "confíe en nosotros, hemos tenido expertos que lo han revisado", ¡es probable que no fueran expertos!

#### Confidencialidad

Para los propósitos de esta sección, la confidencialidad se define como
"ninguna divulgación no autorizada de información".
La criptografía aborda esto mediante la encriptación de los datos en reposo o datos en tránsito,
ocultando la información a todos aquellos que no posean la clave de descifrado.
Los hashes criptográficos (hashes seguros, unidireccionales) previenen la divulgación de contraseñas.

#### Autenticación

La [Autenticación][csauthn] es el proceso de verificar una afirmación de que un sujeto es quien dice ser
a través de alguna evidencia corroborativa proporcionada.
La criptografía es primordial para la autenticación:

1. para proteger la evidencia corroborativa proporcionada (por ejemplo,
    el hash de contraseñas para su posterior almacenamiento)
2. en protocolos de autenticación que a menudo usan criptografía para autenticar entidades directamente
    o para intercambiar credenciales de manera segura
3. para verificar la identidad de una o ambas partes en el intercambio de mensajes,
    por ejemplo, la verificación de identidad dentro de la [Seguridad de la Capa de Transporte][tls] (TLS)

OpenID Connect es ampliamente utilizado como una capa de identidad sobre el protocolo OAuth 2.0,
ver la HOja d Referencia del [Protocolo OAuth 2.0][csoauth].

#### Integridad

La integridad asegura que incluso los usuarios autorizados no hayan realizado alteraciones accidentales
o maliciosas de la información.
La criptografía puede usarse para prevenir la manipulación mediante Códigos de Autenticación de Mensajes (MACs)
o firmas digitales.

El término 'autenticidad del mensaje' se refiere a asegurar la integridad de la información,
a menudo usando encriptación simétrica y claves compartidas,
pero no autentica a la parte que envía.

El término 'encriptación autenticada' también asegura la integridad de la información,
y, si se usa encriptación asimétrica, puede autenticar al remitente.

#### No repudio

El no repudio del remitente asegura que alguien que envía un mensaje no debería poder negar posteriormente
que lo ha enviado.
El no repudio del receptor significa que el receptor de un mensaje no debería poder negar que lo ha recibido.
La criptografía puede usarse para proporcionar no repudio al proporcionar mensajes
o respuestas a mensajes que no se pueden falsificar.

El no repudio es útil para intercambios financieros, de comercio electrónico y contractuales.
Se puede lograr haciendo que el remitente o destinatario firme digitalmente algún registro transaccional único.

#### Atestación

La atestación es el acto de "dar testimonio" o certificar algo para un uso o propósito particular.
La atestación generalmente se discute en el contexto de un Módulo de Plataforma Confiable (TPM),
Gestión de Derechos Digitales (DRM) y Arranque Seguro UEFI.

Por ejemplo, la Gestión de Derechos Digitales está interesada en atestiguar que su dispositivo
o sistema no ha sido comprometido con alguna puerta trasera para permitir
que alguien copie ilegalmente contenido protegido por DRM.

La criptografía puede usarse para proporcionar una cadena de evidencia de que todo está como se espera que esté,
para probar a un contrincante que todo está de acuerdo con las expectativas del contrincante.
Por ejemplo, la atestación remota puede usarse para probar a un contrincante que
realmente está ejecutando el software que afirma estar ejecutando.
La mayoría de las veces la atestación se realiza proporcionando una cadena de firmas digitales comenzando con
un cargador de arranque confiable (firmado digitalmente).

#### Hashes criptográficos

Los hashes criptográficos, también conocidos como resúmenes de mensaje,
son funciones que mapean cadenas de bits de longitud arbitraria
a una cadena de bits de longitud fija conocida como 'valor hash' o 'valor de resumen'.
Estas funciones hash son mapeos de muchos a uno que son funciones de compresión.

Las funciones hash criptográficas se utilizan para proporcionar integridad de datos (es decir,
para detectar la manipulación intencional de datos),
para almacenar contraseñas o frases de paso, y para proporcionar firmas digitales de manera más eficiente
que usando cifrados asimétricos.
Las funciones hash criptográficas también se utilizan para extender un pequeño bit de entropía
para que se puedan construir generadores de números aleatorios seguros.

Cuando se utilizan para proporcionar integridad de datos,
las funciones criptográficas proporcionan dos tipos de integridad:
hashes con clave, a menudo llamados 'códigos de autenticación de mensaje',
y hashes sin clave llamados 'códigos de integridad de mensaje'.

#### Cifrados

Un cifrado es un algoritmo que realiza encriptación o desencriptación.
Los cifrados modernos se pueden categorizar de varias maneras diferentes.
Las distinciones más comunes entre ellos son:

* Si trabajan en un número fijo de bits (cifrados de bloque) o en un flujo continuo de bits (cifrados de flujo)
* Si se usa la misma clave para encriptación y desencriptación (cifrados simétricos)
    o claves separadas para encriptación y desencriptación (cifrados asimétricos)

#### Cifrados Simétricos

Los cifrados simétricos encriptan y desencriptan usando la misma clave.
Esto implica que si una parte encripta datos que una segunda parte debe desencriptar,
esas dos partes deben compartir una clave común.

Los cifrados simétricos vienen en dos tipos principales:

1. Cifrados de bloque, que operan en un bloque de caracteres (típicamente 8 o 16 octetos) a la vez.
    Un ejemplo de cifrado de bloque es AES
2. Cifrados de flujo, que operan en un solo bit (u ocasionalmente un solo byte) a la vez.
    Ejemplos de cifrados de flujo son RC4 (también conocido como ARC4) y Salsa20

Tenga en cuenta que todos los cifrados de bloque también pueden operar en 'modo de transmisión'
seleccionando el modo de cifrado apropiado.

#### Modos de Cifrado

Los cifrados de bloque pueden funcionar en diferentes modos de operación conocidos como "modos de cifrado".
Este modo de cifrado describe algorítmicamente cómo un cifrado opera para aplicar repetidamente
su mecanismo de encriptación o desencriptación a un bloque de cifrado determinado.
Los modos de cifrado son importantes porque tienen un impacto enorme tanto en la confidencialidad
como en la autenticidad del mensaje de los mensajes de texto cifrado resultantes.

Casi todas las bibliotecas criptográficas admiten los cuatro modos de cifrado originales de DES:
ECB, CBC (Encadenamiento de Bloques de Cifrado)
OFB (Retroalimentación de Salida) y CFB (Retroalimentación de Cifrado). Muchas también admiten el modo CTR (Contador).

#### Vector de inicialización

Un vector de inicialización criptográfico (IV) es una entrada de tamaño fijo a la primitiva de encriptación /
desencriptación de un cifrado de bloque.
Se recomienda (y en muchos casos, se requiere) que el IV sea aleatorio o al menos pseudo-aleatorio.

#### Relleno

Excepto cuando operan en modo de transmisión, los cifrados de bloque generalmente operan en bloques de tamaño fijo.
Estos cifrados de bloque también deben operar en mensajes de cualquier tamaño,
no solo aquellos que son un múltiplo sin residuo del tamaño del bloque del cifrado,
por lo que el mensaje puede ser rellenado para ajustarse al siguiente bloque de tamaño fijo.

#### Cifrados asimétricos

Los cifrados asimétricos encriptan y desencriptan con dos claves diferentes.
Una clave generalmente se designa como la clave privada y la otra se designa como la clave pública.
Generalmente, la clave pública se comparte ampliamente y la clave privada se mantiene segura.

Los cifrados asimétricos son más lentos que los cifrados simétricos en varios órdenes de magnitud.
Por esta razón, se utilizan frecuentemente en criptosistemas híbridos, que combinan cifrados asimétricos y simétricos.
En tales criptosistemas híbridos, se genera una clave de sesión simétrica aleatoria
que solo se utiliza durante la duración de la comunicación encriptada.
Esta clave de sesión aleatoria luego se encripta usando un cifrado asimétrico y la clave privada del destinatario.
Los datos de texto plano en sí se encriptan con la clave de sesión.
Luego, todo el paquete (clave de sesión encriptada y mensaje encriptado) se envía junto.
Tanto [TLS][tls] como S/MIME son criptosistemas comunes que utilizan criptografía híbrida.

#### Firma digital

Las firmas digitales son una cadena de datos criptográficamente única que se utiliza
para garantizar la integridad de los datos y probar la autenticidad de algún mensaje digital,
y que asocia algún mensaje de entrada con una entidad originadora.
Un algoritmo de generación de firma digital es un algoritmo criptográficamente fuerte que se utiliza
para generar una firma digital.

#### Protocolo de acuerdo de claves

Los protocolos de acuerdo de claves son protocolos mediante los cuales N partes (generalmente dos)
pueden acordar una clave común sin intercambiar realmente la clave.
Cuando se diseñan e implementan correctamente, los protocolos de acuerdo de claves evitan que los adversarios
aprendan la clave o fuercen su propia elección de clave a las partes participantes.

#### Encriptación a nivel de aplicación

La encriptación a nivel de aplicación se refiere a la encriptación que se considera parte de la aplicación misma;
no implica nada sobre dónde en el código de la aplicación se realiza realmente la encriptación.

#### Derivación de claves

Una función de derivación de claves (KDF) es un algoritmo determinista para
derivar una clave de un tamaño dado a partir de algún valor secreto.
Si dos partes usan el mismo valor secreto compartido y el mismo KDF, siempre deberían derivar exactamente la misma clave.

#### Envoltura de claves

La envoltura de claves es una construcción utilizada con cifrados simétricos para proteger material
de claves criptográficas encriptándolo de una manera especial.
Los algoritmos de envoltura de claves están destinados a proteger las claves mientras se mantienen
en almacenamiento no confiable o mientras se transmiten claves a través de redes de comunicación no seguras.

#### Algoritmos de intercambio de claves

Los algoritmos de intercambio de claves (también conocidos como algoritmos de establecimiento de claves) son protocolos
que se utilizan para intercambiar claves criptográficas secretas
entre un remitente y un receptor de una manera que cumple con ciertas restricciones de seguridad.
Los algoritmos de intercambio de claves intentan abordar el problema de compartir de manera segura
una clave secreta común entre dos partes a través de un canal de comunicación inseguro de manera
que ninguna otra parte pueda obtener acceso a una copia de la clave secreta.

El algoritmo de intercambio de claves más conocido es el Intercambio de Claves Diffie-Hellman.
También existen algoritmos de intercambio de claves autenticados por contraseña.
El intercambio de claves RSA usando PKI o redes de confianza o servidores de claves confiables también se usa comúnmente.

#### Protocolos de transporte de claves

Los protocolos de Transporte de claves son donde una parte genera la clave
y la envía de manera segura al(los) destinatario(s).

#### Protocolos de acuerdo de claves

Los protocolos de Acuerdo de claves son protocolos mediante los cuales N partes (normalmente dos)
pueden acordar una clave común con todas las partes contribuyendo al valor de la clave.
Estos protocolos evitan que los adversarios aprendan la clave
o fuercen su propia elección de clave a las partes participantes.

Referencias

* Serie de Hojas de Referencia de OWASP

  * [Autenticación][csauthn]
  * [Autorización][csauthz]
  * [Almacenamiento Criptográfico][cscs]
  * [Gestión de Claves][kmcs]
  * [Protocolo OAuth 2.0][csoauth]
  * [Seguridad SAML][sscs]
  * [Diseño de Producto Seguro][spdcs]
  * [Protección de Privacidad del Usuario][uppcs]

----

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0404] o [edítelo en GitHub][edit0404].

[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[csoauth]: https://cheatsheetseries.owasp.org/cheatsheets/OAuth2_Cheat_Sheet
[csproject]: https://owasp.org/www-project-cheat-sheets/
[cscs]: https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet
[kmcs]: https://cheatsheetseries.owasp.org/cheatsheets/Key_Management_Cheat_Sheet
[edit0404]: https://github.com/OWASP/DevGuide/blob/main/docs/es/02-foundations/04-crypto-principles.md
[issue0404]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/04-crypto-principles
[sscs]: https://cheatsheetseries.owasp.org/cheatsheets/SAML_Security_Cheat_Sheet
[spdcs]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet
[tls]: https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet
[uppcs]: https://cheatsheetseries.owasp.org/cheatsheets/User_Privacy_Protection_Cheat_Sheet
