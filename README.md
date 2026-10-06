# Amancha-varun
IC engine
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double bore, stroke, clearance;
    double sweptVolume, totalVolume, compressionRatio;
    int choice;

    cout << "===== FOUR-STROKE ENGINE CALCULATOR =====\n";

    cout << "Enter Bore Diameter (mm): ";
    cin >> bore;

    cout << "Enter Stroke Length (mm): ";
    cin >> stroke;

    cout << "Enter Clearance Volume (cm^3): ";
    cin >> clearance;

    // Convert mm to cm
    double bore_cm = bore / 10.0;
    double stroke_cm = stroke / 10.0;

    // Swept volume
    sweptVolume = (M_PI / 4.0) * bore_cm * bore_cm * stroke_cm;

    // Total cylinder volume
    totalVolume = sweptVolume + clearance;

    // Compression ratio
    compressionRatio = totalVolume / clearance;

    do {
        cout << "\n===== MENU =====\n";
        cout << "1. Swept Volume\n";
        cout << "2. Clearance Volume\n";
        cout << "3. Compression Ratio\n";
        cout << "4. Total Cylinder Volume\n";
        cout << "5. Display All Results\n";
        cout << "6. Exit\n";

        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Swept Volume = " << sweptVolume << " cm^3\n";
                break;

            case 2:
                cout << "Clearance Volume = " << clearance << " cm^3\n";
                break;

            case 3:
                cout << "Compression Ratio = " << compressionRatio << ":1\n";
                break;

            case 4:
                cout << "Total Cylinder Volume = " << totalVolume << " cm^3\n";
                break;

            case 5:
                cout << "\n===== RESULTS =====\n";
                cout << "Swept Volume          = " << sweptVolume << " cm^3\n";
                cout << "Clearance Volume      = " << clearance << " cm^3\n";
                cout << "Compression Ratio     = " << compressionRatio << ":1\n";
                cout << "Total Cylinder Volume = " << totalVolume << " cm^3\n";
                break;

            case 6:
                cout << "Program ended.\n";
                break;

            default:
                cout << "Invalid choice! Please try again.\n";
        }

    } while (choice != 6);

    return 0;
}
