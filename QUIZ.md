### How does the DevBoard handle received serial messages? How does this differ from the naïve approach?

A callback function on_receive is register to handle received serial messages. The difference is that we can register different callback functions for different types of events.  

### What does `detached_callback` do? What would happen if it wasn't used?

It detaches a new thread for the execution of the callback function. If not uses, everything will be executed in the main thread and buttons will freeze when reading from/writing to serial.

### What does `LockedSerial` do? Why is it _necessary_?

The lockedSerial wraps the serial Object in a lock, to prevent simultaneous access to its data from multiple threads, which would create a race condition.


