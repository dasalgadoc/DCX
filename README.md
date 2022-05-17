# DCX

<h1> Hello World! </h1>

```python
  pip install pymongo
```

```mermaid
  
  flowchart TB
    
    subgraph CAPS
      ALF -- Envía potenciales acumuladores --> Accumulator
      
      Accumulator -- Notifica acumuladores --> CAPs
      CAPs -- Consulta Acumuladores --> Accumulator
    end
    
    id1([External Sources]) --> ALF
    CAPs -- Notifica límites alcanzados --> id2([Clients])
    id2 -- Consulta caps --> CAPs
   
    click ALF "http://www.google.com.co" "Open this in a new tab" _blank
```

```mermaid
    stateDiagram-v2
        direction TB
        State1: External Sources
        state CAPS {
          ALF --> Accumulator
          Accumulator --> CAPs
          CAPs --> Accumulator
          
          note left of ALF : Recibe mensajes y los filtra
          note left of Accumulator: Valida (DaaS) y acumula si corresponde
          note left of CAPs: Guarda caps y valida límite
        }
        State2: Clients
        
        
        
        State1 --> ALF
        CAPs --> State2
        State2 --> CAPs
```
