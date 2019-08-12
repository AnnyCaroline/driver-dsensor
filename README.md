# Driver for Digital Sensors

## API

### Includes

```
#include "dsensor.ceu"
```

### Code Abstractions

#### ASensor

```
code/await DSensor(var int dataPort, var int? energyPort, var int? time) -> (event (bool) change) -> NEVER;
```

Parameters:

- `int`: analog port for receive data
- `int`: energy port used to turn on and off the sensor
- `int`: time, in ms, the driver waits for the circuit to stabilize

???
- `change`: event emitted when data port value changes

Return:
- `NEVER`: never returns

This code/await turns the energy pin on, waits for the circuit stabilize and enables a interrupt for the data port.