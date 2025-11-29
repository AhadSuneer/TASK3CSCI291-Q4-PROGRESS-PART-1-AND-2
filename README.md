# TASK3CSCI291-Q4-PROGRESS-PART-1-AND-2
Q4 FINAL


#include <iostream>
#include <iomanip>

using namespace std;

// --- PART 1: Template Function ---

/**
 * 1) Template Function: calibrateValue
 * Multiplies an input value by a factor.
 * Updated Signature: S calibrateValue(S x, S factor)
 * Both arguments must be of type S.
 */
template <typename S>
S calibrateValue(S x, S factor) {
    return x * factor;
}

// --- PART 2: Pointer Function ---

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

// --- PART 3: Reference Function ---

/**
 * 3) Function: clampReading
 * Modifies the reading in place to stay within [0, 100].
 * @param r Reference to the double reading.
 */
void clampReading(double& r) {
    if (r < 0) {
        r = 0.0;
    } else if (r > 100) {
        r = 100.0;
    }
}

// --- PART 4: Simple Math Function ---

/**
 * 4) Function: computeDifference
 * Returns the difference between an integer and a double.
 */
double computeDifference(int a, double b) {
    return a - b;
}

// --- MAIN DRIVER ---

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
    // NOTE: Cast calibrationFactor to (int) so both arguments match type 'int'
    int calibratedInt = calibrateValue(intSensorVal, (int)calibrationFactor);
    cout << "Int Calib:    " << right << setw(10) << (double)calibratedInt << endl;
    // 2. Test Double (Part 1 & 2)
    cout << "Dbl Original: " << right << setw(10) << doubleSensorVal << endl;
    // NOTE: Cast calibrationFactor to (double) so both arguments match type 'double'
    double calibratedDouble = calibrateValue(doubleSensorVal, (double)calibrationFactor);
    cout << "Dbl Calib:    " << right << setw(10) << calibratedDouble << endl;
    // Part 2: Adjust
    adjustReading(&calibratedDouble); 
    cout << "Dbl Adjusted: " << right << setw(10) << calibratedDouble << endl;
    // 3. Test Clamp (Part 3)
    clampReading(calibratedDouble);
    cout << "Dbl Clamped:  " << right << setw(10) << calibratedDouble << endl;
    // 4. Test Difference (Part 4)
    double diff = computeDifference(calibratedInt, calibratedDouble);
    cout << "Difference:   " << right << setw(10) << diff << endl;
    return 0;
}
    
