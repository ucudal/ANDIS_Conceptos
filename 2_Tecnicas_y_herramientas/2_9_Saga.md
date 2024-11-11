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
      'fontSize':'8px'
    }
  }
}%%
sequenceDiagram
    Participant Client
    Participant Message Broker
    Participant Service A
    Participant Service B
    Participant Service C

    Client->>Message Broker: Pedido
    Message Broker->>Service A: Pedido para A
    Service A->>Message Broker: Pedido para B
    Message Broker->>Service B: Pedido para B
    Service B->>Message Broker: Pedido para C
    Message Broker->>Service C: Pedido para C
    Service C->>Message Broker: Respuesta
    Message Broker-->>Client: Respuesta

```