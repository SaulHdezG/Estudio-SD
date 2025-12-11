## 🧠 1. Aplicaciones Distribuidas

Una aplicación distribuida es un conjunto de **procesos cooperantes** que se comunican y sincronizan para realizar una tarea común.

**Razones para distribuir:**

- Mayor rendimiento
    
- Reparto de trabajo
    
- Tolerancia a fallos
    
- Sistemas escalables
    

## 🧩 2. Procesos

**¿Qué es un proceso?** Un programa en ejecución con:

- Memoria propia
    
- Variables
    
- Contador de programa
    
- Recursos asignados
    

**Relaciones entre procesos**

- **✔ Independientes:** No comparten datos → no hay interferencia.
    
- **✔ Concurrentes:** Se ejecutan “a la vez” y pueden interferirse.
    
- **✔ Cooperantes:** Necesitan **Comunicación** y **Sincronización**.
    

## 🚀 3. Modelos de Comunicación

Son las reglas que permiten que los procesos intercambien información. Normalmente implementados en un **Middleware** (MPI, CORBA, gRPC, PVM).

## 💬 4. Envío y Recepción de Mensajes

**Elementos:** Emisor, Receptor, Mensaje, Enlace.

### 🔧 Características del enlace

1. **Cardinalidad:** 1→1, 1→N, N→M
    
2. **Capacidad:** 0, Limitada, Ilimitada (teórica)
    
3. **Sentido:** Unidireccional, Bidireccional
    

### 📦 Características del mensaje

- Tipo
    
- Tamaño (fijo / variable)
    
- Por valor o por referencia
    

### 🔄 Tipos de comunicación

- **Directa** vs **Indirecta**
    
- **Simétrica** vs **Asimétrica**
    
- **Síncrona** vs **Asíncrona** (El emisor espera al receptor vs. El emisor no espera).
    

## 👥 5. Comunicación por Grupos

**Usos:**

- Servicios replicados
    
- Sistemas colaborativos
    
- Sistemas de información global
    

**Tipos de grupo:**

- Autocomunicantes
    
- Servidores
    
- Cliente/servidor
    
- Suscripción
    
- Jerárquicos
    

**Métodos de envío:**

- Punto a punto
    
- **Multicast** (a un subconjunto)
    
- **Broadcast** (a todos)
    

## 🧱 6. Orden de Entrega

- **✔ FIFO:** El mismo emisor → los mensajes llegan en el **mismo orden** en que fueron enviados.
    
- **✔ Causal:** Respeta dependencias tipo “sucedió-antes” (garantiza que la causa se vea antes que el efecto).
    
- **✔ Total:** Todos ven los mensajes en el **MISMO orden global**.
    
- **✔ Dependiente de semántica:** Si operaciones son conmutativas, el orden puede variar.
    

## 📞 7. RPC – Remote Procedure Call

Permite llamar funciones remotas como si fueran locales.

### Elementos importantes

- **🟦 Stubs:** Funciones generadas automáticamente por el **IDL Compiler** que:
    
    - **Empaquetan (marshalling)** y **desempaquetan (unmarshalling)**.
        
    - Ocultan los detalles de red.
        
- **🟩 Marshalling / Unmarshalling:**
    
    - **Marshalling** → convertir parámetros a formato para enviar.
        
    - **Unmarshalling** → convertirlos de regreso.
        
    - _Necesario por:_ máquinas diferentes (endianness, tamaños).
        
- **🟨 IDL – Interface Definition Language:** Lenguaje neutral que define:
    
    - Funciones remotas, parámetros, tipos de datos y valores de retorno.
        
    - Usado para generar automáticamente el Stub del cliente y el Stub del servidor.
        
- **🟥 Servicio de localización:** Permite saber dónde está el servidor (dirección fija, registro/directorio, nombre lógico).
    

### Flujo resumido del RPC

1. Cliente llama función.
    
2. Stub cliente convierte parámetros (marshalling).
    
3. Va por red.
    
4. Stub servidor desempaqueta (unmarshalling).
    
5. Ejecuta función real.
    
6. Regresa resultado por mismo camino.
    

## 🧠 8. Memoria Distribuida Compartida (DSM)

Simula memoria compartida en varias máquinas.

**Provee:** variables compartidas, semáforos/mutex, barreras, coherencia.

- **Caso de estudio:** _TreadMarks_ (unidad: palabra, coherencia secuencial, sincronización: candados y barreras).
    

## ⚔️ 9. Paso de Mensajes vs Memoria Distribuida

|Característica|Paso de Mensajes|Memoria Distribuida (DSM)|
|---|---|---|
|**Ventajas**|Eficiente, control total|Más fácil para el programador|
|**Desventajas**|Programación compleja, sincronización manual|Difícil implementación, rendimiento variable|

## 🔥 10. Coherencia de Memoria

Define cómo ven los procesos las actualizaciones.

- **Coherencia Secuencial:** Todos los procesos ven las operaciones en un **orden global único**. Se siente como “una sola memoria”.
    
- **Coherencia Causal:** Solo se mantiene el orden de operaciones que pueden influirse entre sí (dependencias). No requiere un orden total.
    

## 🎯 MINI RESUMEN FINAL (MEMORIZACIÓN)

- **RPC:** IDL + stubs + marshalling
    
- **FIFO:** Orden por emisor
    
- **Causal:** Respeta dependencias
    
- **Total:** Orden global
    
- **DSM:** Simula memoria compartida
    
- **Coherencia secuencial:** Orden único global
    
- **Coherencia causal:** Orden de dependencias
    

# 🗂️ Flashcards: Sistemas Distribuidos

#flashcards

¿Qué es una aplicación distribuida? :: Un conjunto de procesos cooperantes que se comunican y sincronizan para realizar una tarea común.

¿Qué es un proceso cooperante? :: Proceso que trabaja en conjunto con otros y requiere comunicación y sincronización.

Diferencia entre comunicación síncrona y asíncrona :: **Síncrona** → ambos esperan. 

**Asíncrona** → el emisor no espera al receptor.

¿Qué es un stub en RPC? :: Función generada automáticamente que empaqueta y desempaqueta datos para ocultar la red.

¿Qué hace el IDL? :: Define funciones, parámetros y tipos de forma neutral para generar stubs del cliente y servidor.

¿Qué es marshalling? :: Convertir datos a formato transmisible por la red.

¿Qué es coherencia secuencial? :: Todos ven las operaciones en un único orden global, como si fuera una sola memoria.

¿Qué es coherencia causal? :: Mantiene orden solo entre operaciones que tienen una relación de dependencia ("sucedió-antes").

¿Qué caracteriza al modelo FIFO? :: Respeta el orden de mensajes de un mismo emisor.

¿Qué es un sistema DSM? :: Memoria distribuida que simula ser compartida entre varias máquinas.

## 📝 MOCK EXAM – Examen Simulado

> [!INFO] Instrucciones Lee la pregunta y haz clic en "Ver Respuesta" para comprobar si acertaste.

### Preguntas de opción múltiple

1. ¿Cuál de los siguientes NO es un tipo de relación entre procesos? a) Independientes b) Concurrentes c) Cooperantes d) Paralelos
    

> [!success]- Ver Respuesta **Respuesta:** d

2. La cardinalidad 1→N significa: a) Muchos emisores y muchos receptores b) Un emisor, un receptor c) Un emisor, varios receptores d) Muchos emisores, un receptor
    

> [!success]- Ver Respuesta **Respuesta:** c

3. En comunicación síncrona: a) El receptor no necesita estar disponible b) Ambos procesos esperan c) El emisor envía y continúa d) Solo el receptor espera
    

> [!success]- Ver Respuesta **Respuesta:** b (Ambos procesos esperan)

4. ¿Qué componente se genera a partir del IDL? a) Kernel b) Stub c) Proceso remoto d) Buffer de red
    

> [!success]- Ver Respuesta **Respuesta:** b

5. El marshalling se usa para: a) Convertir direcciones IP b) Establecer orden FIFO c) Empaquetar datos para enviarlos d) Crear grupos multicast
    

> [!success]- Ver Respuesta **Respuesta:** c

6. La coherencia secuencial garantiza: a) Un orden global único b) Solo orden por emisor c) Solo relaciones de dependencia d) No hay orden garantizado
    

> [!success]- Ver Respuesta **Respuesta:** a

7. Un sistema DSM ofrece: a) Variables compartidas virtuales b) Solo envío de mensajes c) RPC automático d) Multicast obligatorio
    

> [!success]- Ver Respuesta **Respuesta:** a

8. El modelo causal asegura: a) Orden global b) Orden por emisor c) Orden de mensajes con dependencia d) Ningún tipo de orden
    

> [!success]- Ver Respuesta **Respuesta:** c

9. Un stub en RPC: a) Decide la ruta de la red b) Serializa datos automáticamente c) Asigna direcciones IP d) Define protocolos de red
    

> [!success]- Ver Respuesta **Respuesta:** b

10. ¿Qué grupo recibe mensajes sin responder (uso principal: notificación)? a) Servidores b) Autocomunicantes c) Cliente/servidor d) Suscripción
    

> [!success]- Ver Respuesta **Respuesta:** d

### Preguntas abiertas

11. Explica en una frase “proceso cooperante”.
    

> [!success]- Ver Respuesta Proceso que trabaja con otros hacia una tarea común y necesita comunicación + sincronización.

12. ¿Cuál es la diferencia fundamental entre RPC y el paso de mensajes?
    

> [!success]- Ver Respuesta RPC oculta la red haciendo parecer que se llama una función local (transparencia); el paso de mensajes requiere empaquetar y gestionar manualmente el envío y recepción de datos.

13. Explica la coherencia causal en tus palabras.
    

> [!success]- Ver Respuesta Operaciones que dependen unas de otras (causa y efecto) deben mantener ese orden al ser vistas por cualquier otro proceso del sistema distribuido.

14. ¿Por qué existe el IDL?
    

> [!success]- Ver Respuesta Para describir funciones remotas de forma independiente del lenguaje de programación y generar stubs compatibles en diferentes plataformas.

15. ¿Qué es un multicast y dónde se usa?
    

> [!success]- Ver Respuesta Enviar un mensaje a un subconjunto específico de destinos simultáneamente; se usa en la comunicación por grupos para dirigirse a miembros específicos.

````

---

### Si las flashcards siguen sin funcionar:

1.  **Revisa la configuración del Plugin:** Ve a `Settings` > `Spaced Repetition`. Asegúrate de que la opción **"Separator for inline flashcards"** sea `::`.
2.  **Etiqueta:** Asegúrate de que `#flashcards` esté al principio de la nota o en la configuración del plugin bajo "Tags to include".
3.  **Alternativa:** Si el estilo `::` falla, prueba el estilo "Multiline" cambiando el formato en el texto así:

```markdown
Pregunta
?
Respuesta
````
