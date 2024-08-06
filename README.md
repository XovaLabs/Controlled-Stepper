# Controlled Stepper

## Use the CustomStepper Class in Your Sketch
Now, you can use this class in your Arduino sketch to control your stepper motor.

```cpp
#include <AccelStepper.h>
#include "CustomStepper.h"

CustomStepper stepper(AccelStepper::DRIVER, 2, 3);

void setup() {
    stepper.setMaxSpeed(1000);
    stepper.setAcceleration(500);
}

void loop() {
    // Rotate full circle
    stepper.rotateFull();
    delay(1000);

    // Rotate half circle
    stepper.rotateHalf();
    delay(1000);

    // Rotate semi circle
    stepper.rotateSemiCircle();
    delay(1000);

    // Rotate between two angles
    stepper.rotateBetweenAngles(90, 270);
    delay(1000);
}
```

### Explanation of the CustomStepper Class
1. **Constructor**: Initializes the stepper motor with the specified interface and pins.
2. **rotateFull()**: Rotates the motor a full circle (360 degrees).
3. **rotateHalf()**: Rotates the motor half a circle (180 degrees).
4. **rotateSemiCircle()**: Rotates the motor half a circle (180 degrees).
5. **rotateBetweenAngles(float startAngle, float endAngle)**: Rotates the motor from the current position to an angle between the specified start and end angles.
6. **rotateDegrees(float degrees)**: Converts degrees to steps and moves the motor.
7. **degreesToSteps(float degrees)**: Helper function to convert degrees to steps, assuming 200 steps per revolution.

### Notes
- Make sure to set the correct number of steps per revolution in the `degreesToSteps` function if your stepper motor has a different specification.
- Adjust the pins and motor interface type as per your hardware configuration.

