# TASK3CSCI291-Q4-PROGRESS-PART-1-AND-2
Q4 PROGRESS PART 1 AND 2
#include <iostream>
#include <iomanip>

using namespace std;

/*
1) Template Function: calibrateValue
Multiplies an input value by a factor.
@tparam S The type of the input value (e.g., int, double)
@param x A constant reference to the input value
@param factor A char type numerical value used as a multiplier
@return The product of x and factor, of type S */

template <typename S>
S calibrateValue(S& x, S factor) {
    return x * factor;
}
/* 2) Function: adjustReading
 Adds an offset to a sensor reading in-place using a pointer.
 @param value A pointer to a double representing the sensor reading
  @param offset A double to add to the reading (defaults to 1.25)
 */
*value, double offset = 1.25) {
    if (value != nullptr) {
        *value = *value + offset;
    }
}
int main() {
    // Variables to store sensor data
    int intSensorVal;
    double doubleSensorVal;
    char calibrationFactor = 2; 
cout << "--- Laboratory Sensor Input ---" << endl;
    cout << "Enter integer sensor value: ";
    cin >> intSensorVal;
    cout << "Enter double sensor value: ";
    cin >> doubleSensorVal;
    cout << endl;
    cout << fixed << showpoint << setprecision(4);
    cout << "--- Calibration Results ---" << endl;
    cout << "Format: [Right Aligned, Width 10, Precision 4]" << endl << endl;
    cout << "1. Integer Sensor:" << endl;
    cout << "Original: " << right << setw(10) << (double)intSensorVal << endl; // Cast to double for consistent precision display
    int calibratedInt = calibrateValue(intSensorVal, calibrationFactor);
    cout << "Calibrated: " << right << setw(10) << (double)calibratedInt << " (Factor: " << (int)calibrationFactor << ")" << endl;
    cout << endl;
    cout << "2. Double Sensor:" << endl;
    cout << "Original: " << right << setw(10) << doubleSensorVal << endl;
    double calibratedDouble = calibrateValue(doubleSensorVal, calibrationFactor);
    cout << "Scaled:   " << right << setw(10) << calibratedDouble << " (Factor: " << (int)calibrationFactor << ")" << endl;
    adjustReading(&calibratedDouble);
    cout << "Adjusted 1: " << right << setw(10) << calibratedDouble << " (Offset: Default 1.25)" << endl;
    double customOffset = 5.0;
    adjustReading(&calibratedDouble, customOffset);
    cout << "Adjusted 2: " << right << setw(10) << calibratedDouble << " (Offset: 5.0000)" << endl;
    return 0;
}
    
    
