# 5 Unidades temáticas

## 5.2 Análisis y diseño de aplicaciones II

### 5.2.4 Patrones de arquitectura

#### Lecturas

1. Lee los sitios referenciados en los siguientes documentos de este repositorio
   para patrones para disponibilidad:

    * [Bulkhead](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Bulkhead.md)

    * [Circuit Breaker](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Circuit_breaker.md)

    * [Competing Consumers](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Competing_Consumers.md)

    * [Event Sourcing](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Event_Sourcing.md)

    * [Health Endpoint Monitoring](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Health_Endpoint_Monitoring.md)

    * [Rate Limiting](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Rate_Limiting.md)

    * [Retry](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Retry.md)

    * [Throttling](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Throttling.md)

2. Lee los sitios referenciados en los siguientes documentos de este repositorio
   para patrones para el rendimiento:

    * [Cache-Aside](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Cache_Aside.md)

    * [Queue-Based Load Leveling](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Queue-Based_Load_Leveling.md)

    * [Competing Consumers](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Competing_Consumers.md)

    * [Publisher/Subscriber](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Publisher_Subscriber.md)

    * [Asynchronous Request-Reply](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Asynchronous_Request_Reply.md)

    * [CQRS](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_CQRS.md)

    * [Materialized View](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Materialized_View.md)

3. Lee los sitios referenciados en los siguientes documentos de este repositorio
   para patrones para la seguridad:

    * [Gatekeeper](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Gatekeeper.md)

    * [Federated Identity](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Federated_Identity.md)

    * [Gateway Offloading](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Gateway_Offloading.md)

    * [Sidecar](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Sidecar.md)

    * [Valet Key](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Valet_Key.md)

4. Lee los sitios referenciados en los siguientes documentos de este repositorio
   para patrones para la facilidad de modificación y de despliegue

    * [Deployment
      Stamps](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Deployment_Stamps.md)

    * [External Configuration
      Store](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_External_Configuration_Store.md)

    * [Messaging
      Bridge](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Messaging_Bridge.md)

    * [Strangler
      Fig](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura/2_09_Strangler_Fig.md)

5. Lee lo siguiente sobre patrones de facilidad de modificación y despliegue:

    * Arquitecturas de micro-servicios en [^4] y [^5].

    * Blue/green deployment en [^6]. Opcionalmente mira también [10^].

    * Rolling upgrade en [^7].

    * Canary testing en [^8].

    * A/B testing en [^9].

[^4]: Microsoft. (2024). Microservice architecture style. Disponible
  [aquí](https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices)

[^5]: Lewis, J. & Fowler, M. (2014). Microservices. Disponible
  [aquí](https://martinfowler.com/bliki/BlueGreenDeployment.html)

[^6]: Fowler, M. (2010). Blue Green Deployment. Disponible
  [aquí](https://martinfowler.com/bliki/BlueGreenDeployment.html)

<!-- cSpell:ignore Wolski Laiho Fabijan Dmitriev Olsson -->

[^7]: Wolski, A. & Laiho, K. (2004). Rolling Upgrades for Continuous Services.
  Disponible
  [aquí](https://link-springer-com.proxy.timbo.org.uy/chapter/10.1007/978-3-540-30225-4_13)
  vía Timbó.

[^8]: Sato, D. (2014). Canary Release. Disponible
  [aquí](https://martinfowler.com/bliki/CanaryRelease.html?ref=wellarchitected)

[^9]: Fabijan, A., Dmitriev, P., Olsson, H. H., & Bosch, J. (2017). The
    evolution of continuous experimentation in software product development:
    From data to a data-driven organization at scale. In Proceedings of the 39th
    International Conference on Software Engineering (pp. 770-780). IEEE Press.
    Disponible
    [aquí](https://www.researchgate.net/publication/317006885_The_Evolution_of_Continuous_Experimentation_in_Software_Product_Development).

[^10] Microsoft. (2025). Blue-green deployment in Azure Container Apps.
Microsoft Learn. Recuperado 15 de September de 2025 de
[aquí](https://learn.microsoft.com/en-us/azure/container-apps/blue-green-deployment?pivots=azure-cli).

#### Lecturas complementarias

<!-- cSpell:ignore Bachmann Nord -->

1. Lee lo siguiente de [^1]:

    * Sección 4.4, **Patterns for Availability**

    * Sección 9.4, **Patterns for Performance**

    * Sección 10.4, **Patterns for Safety**

    * Sección 11.4, **Patterns for Security**

    * Sección 8.4, **Patterns for Modifiability**

    * Sección 5.4, **Patterns for Deployability**

2. Lee en el sitio de [Azure Well-Architected
   Framework](https://learn.microsoft.com/en-us/azure/well-architected/):

    * [Cloud design patterns that support
      reliability](https://learn.microsoft.com/en-us/azure/well-architected/reliability/design-patterns).

    * [Cloud design patterns that support performance
      efficiency](https://learn.microsoft.com/en-us/azure/well-architected/performance-efficiency/design-patterns).

    * [Cloud design patterns that support
      security](https://learn.microsoft.com/en-us/azure/well-architected/security/design-patterns).

3. En el Carnegie Mellon University Software Engineering Institute's Insights
  Blog [Tactics and Patterns for Software
  Robustness](https://insights.sei.cmu.edu/blog/tactics-and-patterns-for-software-robustness/).

4. En The Open Group [Security Design
  Patterns](https://pubs.opengroup.org/onlinepubs/9299969899/toc.pdf).

5. Bachmann, F., Bass, L. & Nord, R. (2007). Modifiability Tactics.
  CMU/SEI-2007-TR-002 disponible
  [aquí](https://insights.sei.cmu.edu/documents/778/2007_005_001_14858.pdf).

6. Kazman, R. (2022). Two Categories of Architecture Patterns for Deployability.
  Carnegie Mellon University, Software Engineering Institute's Insights Blog.
  Disponible
  [aquí](https://insights.sei.cmu.edu/blog/two-categories-of-architecture-patterns-for-deployability/).

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4th edition. Addison-Wesley.
