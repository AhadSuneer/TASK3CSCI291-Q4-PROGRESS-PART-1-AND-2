# TASK3CSCI291-Q4-PROGRESS-PART-1-AND-2
Q4 PROGRESS PART 1 AND 2


#include <iostream>
#include <iomanip>

using namespace std;

// PART 1: Template Function

/**
 * 1) Template Function: calibrateValue
 * Multiplies an input value by a factor.
 * Correct Signature: Second parameter must be 'char', not 'S'.
 */
template <typename S>
S calibrateValue(S x, S factor) {
    return x * factor;
}

// PART 2: Pointer Function

/**
 * 2) Function: adjustReading
 * Adds an offset to a sensor reading.
 * Note: Must return void.
 */
void adjustReading(double* value, double offset = 1.25) {
    if (value != nullptr) {
        *value = *value + offset;
    }
}

// MAIN DRIVER

int main() {
    // Variables
    int intSensorVal;
    double doubleSensorVal;
    char calibrationFactor = 2; // Treated as number 2
    // Input
    cout << "--- Laboratory Sensor Input ---" << endl;
    cout << "Enter integer sensor value: ";
    cin >> intSensorVal;
    cout << "Enter double sensor value: ";
    cin >> doubleSensorVal;
    cout << endl;
    // Formatting
    cout << fixed << showpoint << setprecision(4);
    cout << "--- Calibration Results ---" << endl;
    // 1. Test Integer (Part 1)
    // Cast to double for display width consistency
    cout << "Int Original: " << right << setw(10) << (double)intSensorVal << endl;
    int calibratedInt = calibrateValue(intSensorVal, calibrationFactor);
    cout << "Int Calib:    " << right << setw(10) << (double)calibratedInt << endl;
    // 2. Test Double (Part 1 & 2)
    cout << "Dbl Original: " << right << setw(10) << doubleSensorVal << endl;
    double calibratedDouble = calibrateValue(doubleSensorVal, calibrationFactor);
    cout << "Dbl Calib:    " << right << setw(10) << calibratedDouble << endl;
    cout << "Dbl Adjusted: " << right << setw(10) << calibratedDouble << endl;
    return 0;
}
    
    
