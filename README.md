# agentes-y-control-versi-n-Groq
# Arquitectura del agente
El sistema utiliza un modelo de lenguaje Groq, herramientas especializadas y controles de seguridad para gestionar solicitudes de clientes. La confirmación de pedidos requiere aprobación humana.


            CLIENTE
                |
                v
       Protección de datos PII
                |
                v
          AGENTE GROQ
                |
       +--------+--------+
       |        |        |
       v        v        v
    Buscar   Cotizar   Envío
       |        |        |
       +--------+--------+
                |
                v
       CONFIRMAR PEDIDO
                |
                v
        PAUSA DE CONTROL
                |
         +------+------+
         |             |
       APPROVE       REJECT
         |             |
         v             v
    Registrar       No registrar
      pedido          pedido



# Descripción del flujo:
1. El cliente realiza una solicitud.
2. El middleware protege información personal.
3. El agente interpreta la intención.
4. Selecciona las herramientas necesarias.
5. Verifica productos, stock, cotización y envío.
6. Si se solicita confirmar un pedido, se activa una pausa.
7. Una persona autorizada aprueba o rechaza la operación.
8. El agente continúa según la decisión recibida.
