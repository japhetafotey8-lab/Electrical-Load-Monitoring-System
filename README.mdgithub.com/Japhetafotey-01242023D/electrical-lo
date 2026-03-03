#include <iostream>
#include <vector>
#include <iomanip>

using namespace std;

class Appliance {
private:
    int id;
    string name;
    double power;   // Watts
    double hours;   // Usage per day

public:
    Appliance(int i, string n, double p, double h) {
        id = i;
        name = n;
        power = p;
        hours = h;
    }

    int getId() const { return id; }
    string getName() const { return name; }
    double getPower() const { return power; }
    double getHours() const { return hours; }

    double calculateEnergy() const {
        return (power * hours) / 1000.0;  // kWh
    }

    void display() const {
        cout << left << setw(5) << id
             << setw(12) << name
             << setw(12) << power
             << setw(12) << hours
             << setw(12) << calculateEnergy()
             << endl;
    }
};

vector<Appliance> appliances;

void loadDefaultAppliances() {
    appliances.push_back(Appliance(1, "Fan", 75, 8));
    appliances.push_back(Appliance(2, "TV", 120, 5));
    appliances.push_back(Appliance(3, "Fridge", 200, 24));
}

void viewAppliances() {
    cout << "\nID   Name        Power(W)   Hours       Energy(kWh)\n";
    cout << "--------------------------------------------------------\n";

    for (size_t i = 0; i < appliances.size(); i++) {
        appliances[i].display();
    }
}

void calculateBilling() {
    double tariff;
    cout << "\nEnter Electricity Tariff (per kWh): ";
    cin >> tariff;

    if (tariff <= 0) {
        cout << "Tariff must be positive!\n";
        return;
    }

    double totalEnergy = 0;

    for (size_t i = 0; i < appliances.size(); i++) {
        totalEnergy += appliances[i].calculateEnergy();
    }

    double totalCost = totalEnergy * tariff;

    cout << fixed << setprecision(2);
    cout << "\nTotal Energy Consumption: " << totalEnergy << " kWh\n";
    cout << "Total Electricity Cost: " << totalCost << endl;
}

int main() {

    loadDefaultAppliances();   // Load preset appliances

    int choice;

    do {
        cout << "\n===== Electrical Load Monitoring System =====\n";
        cout << "1. View Appliances\n";
        cout << "2. Calculate Billing\n";
        cout << "3. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            viewAppliances();
            break;
        case 2:
            calculateBilling();
            break;
        case 3:
            cout << "Exiting program...\n";
            break;
        default:
            cout << "Invalid choice!\n";
        }

    } while (choice != 3);

    return 0;
}
# Electrical-Load-Monitoring-System
Electrical Load Monitoring and Billing Simulator
# Electrical Load Monitoring and Billing Simulator

## 📘 Course Information
- Name: Japhet Afotey Nmai
- Student ID:01242023D
- Programme: HND Electrical Engineering (Level 200)
- Course: EEE 227 (PT)
- Assessment: Mid-Semester Capstone Project


---

## 📌 Project Description

This project is a console-based C++ application that simulates:

- Electrical load monitoring
- Energy consumption calculation
- Electricity billing estimation

The system allows users to register appliances, calculate total energy consumption, and compute electricity costs based on a given tariff.

---

## ⚙️ Features

### Appliance Management
- Register new appliance
- View all appliances
- Search appliance by name

### Load & Energy Calculation
- Stores power rating (Watts)
- Stores daily usage hours
- Calculates energy in kWh
- Computes total energy consumption

### Billing System
- Accepts electricity tariff per kWh
- Calculates total cost
- Generates billing summary file

### File Storage
- Saves appliance data to `appliances.txt`
- Loads saved data when program restarts
- Saves billing summary to `billing_summary.txt`

---

## 🧮 Energy Formula Used

Energy (kWh) = (Power in Watts × Usage Hours) / 1000

Cost = Total Energy × Tariff

---

## 🗂 Repository Structure
