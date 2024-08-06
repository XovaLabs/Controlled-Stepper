#include <AccelStepper.h>

class CustomStepper : public AccelStepper {
public:
    CustomStepper(uint8_t interface = AccelStepper::DRIVER, uint8_t pin1 = 2, uint8_t pin2 = 3, uint8_t pin3 = 4, uint8_t pin4 = 5)
        : AccelStepper(interface, pin1, pin2, pin3, pin4) {}

    void rotateFull() {
        rotateDegrees(360);
    }

    void rotateHalf() {
        rotateDegrees(180);
    }

    void rotateSemiCircle() {
        rotateDegrees(180);
    }

    void rotateBetweenAngles(float startAngle, float endAngle) {
        float currentPositionInDegrees = currentPosition() * 360.0 / 200.0; // Assuming 200 steps per revolution
        float distanceToMove = endAngle - startAngle;
        float targetPositionInDegrees = currentPositionInDegrees + distanceToMove;

        if (distanceToMove > 0) {
            moveTo(degreesToSteps(targetPositionInDegrees));
        } else {
            moveTo(degreesToSteps(targetPositionInDegrees));
        }
        runToPosition();
    }

private:
    void rotateDegrees(float degrees) {
        long steps = degreesToSteps(degrees);
        move(steps);
        runToPosition();
    }

    long degreesToSteps(float degrees) {
        return (long)(degrees * 200.0 / 360.0); // Assuming 200 steps per revolution
    }
};
