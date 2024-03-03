# GIT

##  git

# GITHUB
1. git init
2. git add
3. git commit -m "message"

# DART INTRODUCTION
### What is dart?

import 'dart:io';

void main() {
  // Product list
  Map<String, int> products = {
    'dell': 20000,
    'roshiba': 30000,
    'mac': 50000
  };

  // Delivery options
  Map<String, int> deliveryOptions = {'home': 1000, 'pickup': 0};

  // Packing options
  Map<String, int> packingOptions = {'plastic': 500, 'bag': 1000, 'gift box': 5000};

  // Location options
  Map<String, int> locationOptions = {'ktm': 13, 'ltp': 0, 'bkt': 0};

  // ATM details
  String atmPin = '1234';
  int atmAmount = 10000;

  // Call charges
  Map<String, double> callCharges = {
    'ntc to ntc': 2.5,
    'ntc to ncell': 3.5,
    'ncell to ncell': 1,
    'ncell to ntc': 5.5
  };

  // Product selection
  print('Product List:');
  products.forEach((key, value) => print('${key}: Rs.${value}'));
  print('Enter product name:');
  String productName = stdin.readLineSync()!.toLowerCase();

  // Quantity
  print('Enter quantity:');
  int quantity = int.parse(stdin.readLineSync()!);

  // Delivery option
  print('Delivery Option:');
  deliveryOptions.forEach((key, value) => print('${key}: Rs.${value}'));
  print('Enter delivery option:');
  String deliveryOption = stdin.readLineSync()!.toLowerCase();

  // Packing
  print('Packing:');
  packingOptions.forEach((key, value) => print('${key}: Rs.${value}'));
  print('Enter packing option:');
  String packingOption = stdin.readLineSync()!.toLowerCase();

  // Location
  print('Location:');
  locationOptions.forEach((key, value) => print('${key}: Rs.${value}'));
  print('Enter location:');
  String location = stdin.readLineSync()!.toLowerCase();

  // ATM transaction
  print('Enter ATM PIN:');
  String enteredPin = stdin.readLineSync()!;
  print('Enter ATM amount:');
  int enteredAmount = int.parse(stdin.readLineSync()!);

  // Call charges
  print('Enter call duration:');
  int callDuration = int.parse(stdin.readLineSync()!);
  print('Enter call type (ntc to ntc, ntc to ncell, ncell to ncell, ncell to ntc):');
  String callType = stdin.readLineSync()!.toLowerCase();

  // Calculate total cost
  int productCost = products[productName]! * quantity;
  int deliveryCost = deliveryOptions[deliveryOption]!;
  int packingCost = packingOptions[packingOption]!;
  int locationTax = locationOptions[location]!;
  int atmFee = (enteredPin == atmPin && enteredAmount == atmAmount) ? 0 : 100;
  double callCharge = callCharges[callType]! * callDuration;

  // Calculate grand total
  double grandTotal = productCost + deliveryCost + packingCost + locationTax + atmFee + callCharge;

  // Display results
  print('Product Cost: Rs.${productCost}');
  print('Delivery Cost: Rs.${deliveryCost}');
  print('Packing Cost: Rs.${packingCost}');
  print('Location Tax: Rs.${locationTax}');
  print('ATM Fee: Rs.${atmFee}');
  print('Call Charge: Rs.${callCharge}');
  print('Grand Total: Rs.${grandTotal}');
}



