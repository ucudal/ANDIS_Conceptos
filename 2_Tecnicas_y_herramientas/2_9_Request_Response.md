
# 2 Técnicas y herramientas

## 2.9 Patrones de arquitectura

### Request/Response

> ![](/assets/question.svg)<span style="color:#0969DA"> Problema</span></br>
> ¿Cuál es la forma más simple para que un servicio procese un pedido y provea
> un resultado?

> ![](/assets/solution.svg)<span style="color:#0969DA"> Solución</span></br>
> Procesar los pedidos cuando son recibidos y retornar los resultados en la
> misma conexión con el cliente

Este documento está basado en [^1].

[^1]: Daigneau, R.; Robinson, I. (2012). Service Design Patterns. Addison-Wesley.

```mermaid
%%{
  init: {
    'theme': 'base',
    'themeVariables': {
       'mainBkg': 'transparent',
      'primaryColor': 'transparent',
      'primaryTextColor': '#006EAF',
      'primaryBorderColor': '#006EAF',
      'lineColor': '#006EAF',
      'secondaryColor': '#006100',
      'fontFamily':'Helvetica',
      'fontSize':'8px',
      'noteBkgColor':'transparent',
      'noteTextColor':'#006EAF'
    }
  }
}%%
sequenceDiagram
    Participant Client
    Participant Service

    rect rgba(0, 0, 0, 0.5)
        note over Client, Service: Conexión
        Client->>Service: Pedido
        Service-->>Client: Respuesta
    end
```


