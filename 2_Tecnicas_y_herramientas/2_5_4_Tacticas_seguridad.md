# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.4 Tácticas para la seguridad

Una forma de pensar acerca de la seguridad en un sistema es mirar la seguridad
física. Las instalaciones seguras limitan el acceso a su interior —por ejemplo,
mediante el uso de vallas y puntos de control de acceso—, cuentan con métodos para
detectar intrusos —como exigir a los visitantes autorizados que porten tarjetas
de identificación—, poseen mecanismos disuasorios —como la presencia de cámaras
de vigilancia—, tienen sistemas de respuesta —por ejemplo, activación automática
de alarmas— y disponen de mecanismos de recuperación —como sistemas de respaldo
en ubicaciones remotas—. Estas medidas se agrupan en cuatro categorías de
tácticas: detección, resistencia, reacción y recuperación[^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

La lista de tácticas está tomada de [^1]:

* **Detectar la intrusión**. Consiste en comparar patrones de tráfico o de
  llamados contra un conjunto conocido de patrones de comportamiento malicioso.
  Los patrones puede estar basados en características del protocolo, de los
  llamados, del contenido de los mensajes —*payload*—, origen, destino, etc.

  Vean además [Recommendations for monitoring and threat
  detection](https://learn.microsoft.com/en-us/azure/well-architected/security/monitor-threats)
  en Azure Well-Architected Framework.

* **Detectar la denegación del servicio**. Es identificar cuándo se está
  llevando a cabo un ataque que intenta hacer que el sistema sea inaccesible
  para los usuarios legítimos. Por ejemplo, monitorear el tráfico de red para
  identificar un aumento inusual en las solicitudes que podrían indicar un
  ataque DDoS —denegación de servicio distribuida, o *distributed denial or
  service*—.

  Vean además [Recommendations for networking and
  connectivity](https://learn.microsoft.com/en-us/azure/well-architected/security/networking)
  en Azure Well-Architected Framework.

* **Verificar la integridad de los mensajes**. Consiste en asegurar que los
  mensajes no han sido alterados durante la transmisión, mediante el uso de
  sumas de verificación —*hashes*— o firmas digitales para verificar la
  integridad de los mensajes.

  Vean además [Recommendations for data
  encryption](https://learn.microsoft.com/en-us/azure/well-architected/security/encryption)
  en Azure Well-Architected Framework.

* **Detectar anomalías en la entrega de mensajes**. Es identificar
  comportamientos inusuales o anómalos en la entrega de mensajes, que podrían
  sugerir un ataque de intermediario —*man-in-the-middle*—.

* **Identificar actores**. Consiste en identificar —conocer la identidad— de los
  diferentes actores —usuarios o componentes— que interactúan con un componente
  de la arquitectura de software. Los usuarios son identificador típicamente
  mediante un identificador de usuario —o *user id*—, pero también se puede usar
  direcciones IP u otros mecanismos.

  Vean además [Recommendations for identity and access
  management](https://learn.microsoft.com/en-us/azure/well-architected/security/identity-access)
  en Azure Well-Architected Framework.

* **Autenticar actores**. Es el proceso de verificar la identidad de los actores
  para asegurar que son quienes dicen ser. Las contraseñas, las contraseñas de
  un solo uso —OTP o *one time password*, los certificados digitales, la
  autenticación de dos factores —2FA o *two factors authentication*— y
  la identificación biométrica proporcionan un medio para la autenticación.

  Vean además [Recommendations for identity and access
  management](https://learn.microsoft.com/en-us/azure/well-architected/security/identity-access)
  en Azure Well-Architected Framework.

* **Autorizar actores**. Consiste en poder determinar qué acciones o recursos
  tiene permitido acceder un actor autenticado. El acceso puede ser limitado por
  actor o por rol.

  Vean además [Recommendations for identity and access
  management](https://learn.microsoft.com/en-us/azure/well-architected/security/identity-access)
  en Azure Well-Architected Framework.

* **Limitar el acceso**. Es limitar el acceso a recursos computacionales, ya sea
  restringiendo la cantidad de puntos de acceso, como el tipo de tráfico
  permitido a través de los puntos de acceso; en ambos casos de reduce la
  superficie de ataque del componente arquitectónico. Un ejemplo es la DMZ.

  Vean además [Recommendations for building a segmentation
  strategy](https://learn.microsoft.com/en-us/azure/well-architected/security/segmentation)
  en Azure Well-Architected Framework y [Implement a secure hybrid
  network](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/dmz/secure-vnet-dmz)
  en Azure Architecture Center.

* **Limitar la exposición**. Consiste en minimizar la cantidad de información o
  servicios que se exponen a través de un punto de acceso, para minimizar los
  efectos de los daños de un ataque.

* **Cifrar los datos**. Consiste en transformar los datos de forma que solo
  pueda ser leído por aquellos que posean la clave de descifrado. El cifrado
  puede ser simétrico —ambas partes tienen la misma clave— o asimétrico
  —mediante un mecanismo de clave pública y privada—.

  Vean además [Recommendations for data
  encryption](https://learn.microsoft.com/en-us/azure/well-architected/security/encryption)
  en Azure Well-Architected Framework.

* **Separar entidades**. Es aislar diferentes componentes o datos para evitar
  que un compromiso en uno de ellos afecte a los demás. Los componentes de
  cómputo se pueden separar en máquinas físicas, máquinas virtuales,
  contenedores, etc. Los datos sensibles pueden estar separados de los datos
  no-sensibles.

* **Validar la entrada**. Consiste en verificar que los datos de entrada cumplen
  con los formatos y valores esperados para prevenir ataques como la inyección
  SQL o *cross-site scripting*.

  Vean además [Recommendations for hardening
  resources](https://learn.microsoft.com/en-us/azure/well-architected/security/harden-resources)
  en Azure Well-Architected Framework.

* **Cambiar la configuración de las credenciales**. Es modificar la
  configuración de seguridad predeterminada de los componentes de la
  infraestructura cuando se ponen en funcionamiento y cambiarla también
  periódicamente. Por ejemplo, forzar a los usuarios a cambiar sus contraseñas
  después de cierto tiempo.

* **Revocar el acceso**. Consiste en limitar el acceso de las credenciales
  —aún las legítimas— cuando se sospecha que ha ocurrido un ataque.

* **Restringir el ingreso**. Consiste en impedir el acceso de las credenciales
  cuando se sospecha que ha ocurrido un ataque. Por ejemplo, bloquear a un
  usuario luego de varios intentos fallidos de autenticación.

* **Informar a los actores**. Es notificar a los
  [interesados](/4_Conceptos/4_Interesado.md) relevantes sobre un intento de
  ataque. Por ejemplo, enviar un correo electrónico a los usuarios cuando se
  detecta un intento de acceso no autorizado a sus cuentas.

* **Auditar**. Consiste en registrar y revisar las acciones de los actores para
  detectar y prevenir actividades maliciosas.

* **No-repudio**. Es asegurar que un actor no pueda negar haber realizado una
  acción específica. Por ejemplo, usar firmas digitales para garantizar que un
  usuario no pueda negar haber enviado un correo electrónico específico.
