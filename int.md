# Driver for Digital Sensors: External Interrupts

### Includes

```
#include "dsensor-intX.ceu"
```

### Code Abstractions

```
code/await DSensor-INTX(var int dataPort, var int? energyPort, var int? time, var int? debounce) -> (event (bool) change) -> NEVER;
```

Parameters:

- `int`: digital port for receive data
- `int`: energy port used to turn on and off the sensor
- `int?`: time, in ms, the driver waits for the circuit to stabilize
- `int?`: debouce time, in ms

Public fields:
- `event (bool)`: event emitted when data port value changes

Return:
- `NEVER`: never returns

This code/await turns the energy pin on, waits for the circuit stabilize and enables a interrupt for the data port.