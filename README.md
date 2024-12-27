# BMI Calculator
![BMI Project cover](https://github.com/pbisht2105/BMI-Calculator/blob/main/BMI%20Calculator%20Project.png)

## What the code does

This code is a **BMI (Body Mass Index) Calculator** that:
1. Asks the user to choose between **Imperial** (pounds and inches) or **Metric** (kilograms and meters) units for height and weight.
2. Converts between various units to help the user understand the input values (e.g., 1 inch = 2.54 cm, 1 pound = 0.453592 kg).
3. Accepts the user's height and weight based on their unit choice.
4. Calculates the **BMI** using the provided formulas for both Imperial and Metric systems.
5. Categorizes the BMI result into different categories (Underweight, Normal weight, Overweight, Obese, etc.) and provides advice based on the user's BMI.

## Code

```python
# Information about unit conversions with examples
print("Unit Conversions:")
print("1 inch = 2.54 centimeters (cm)")  # Inches to centimeters
print("1 pound (lbs) = 0.453592 kilograms (kg)")  # Pounds to kilograms
print("1 meter = 100 centimeters (cm)")  # Meters to centimeters
print("1 kilogram = 1000 grams (g)")  # Kilograms to grams
print("\nThese are the conversion factors to help you understand the units.")

# Ask for the user's name
name = input("Enter your Name: ")

# Ask the user to choose units: imperial (pounds/inches) or metric (kg/meters)
unit = input("Please choose your unit system:\n- Type 'imperial' for pounds and inches\n- Type 'metric' for kilograms and meters\n").strip().lower()

# Validate the unit input
while unit not in ["imperial", "metric"]:
    unit = input("Invalid input. Please enter 'imperial' or 'metric': ").strip().lower()

# Get user input for weight and height based on the chosen unit system
if unit == "imperial":
    # Ask for weight in pounds and height in inches
    while True:
        try:
            weight = float(input("Enter your weight in pounds(lbs) (e.g., 150). 1 pound = 0.453592 kilograms: "))
            if weight <= 0:
                raise ValueError("Weight must be a positive number.")
            break
        except ValueError as e:
            print(f"Invalid input for weight: {e}. Please try again.")
    
    while True:
        try:
            height = float(input("Enter your height in inches (e.g., 70). 1 inch = 2.54 centimeters: "))
            if height <= 0:
                raise ValueError("Height must be a positive number.")
            break
        except ValueError as e:
            print(f"Invalid input for height: {e}. Please try again.")
    
elif unit == "metric":
    # Ask for weight in kilograms and height in meters
    while True:
        try:
            weight = float(input("Enter your weight in kilograms (e.g., 68). 1 kilogram = 1000 grams: "))
            if weight <= 0:
                raise ValueError("Weight must be a positive number.")
            break
        except ValueError as e:
            print(f"Invalid input for weight: {e}. Please try again.")
    
    while True:
        try:
            height = float(input("Enter your height in meters (e.g., 1.75). 1.75 meter = 175 centimeters: "))
            if height <= 0:
                raise ValueError("Height must be a positive number.")
            break
        except ValueError as e:
            print(f"Invalid input for height: {e}. Please try again.")

# Calculate BMI based on the chosen unit system
if unit == "imperial":
    BMI = (weight / (height * height)) * 703
elif unit == "metric":
    BMI = weight / (height * height)

# Print the calculated BMI
print(f"\n{name}, your BMI is {BMI:.2f}.")

# Determine the BMI category and health risk level
if BMI > 0:
    if BMI < 18.5:
        print(f"{name}, you are Underweight.")
        print("Health Risk: Minimal")
        print("Advice: Consider gaining weight healthily. Speak with a healthcare provider for personalized advice.")
    elif BMI <= 24.9:
        print(f"{name}, you are Normal weight.")
        print("Health Risk: Minimal")
        print("Advice: Great! Maintain a balanced diet and exercise regularly to keep your weight stable.")
    elif BMI <= 29.9:
        print(f"{name}, you are Overweight.")
        print("Health Risk: Increased")
        print("Advice: Incorporate more physical activity and a balanced diet to lose weight gradually.")
    elif BMI <= 34.9:
        print(f"{name}, you are Obese.")
        print("Health Risk: High")
        print("Advice: Losing weight can reduce health risks. Consult a professional for a weight management plan.")
    elif BMI <= 39.9:
        print(f"{name}, you are Severely Obese.")
        print("Health Risk: Very High")
        print("Advice: Severe obesity requires medical attention. Speak to a healthcare provider for options.")
    else:
        print(f"{name}, you are Morbidly Obese.")
        print("Health Risk: Extremely High")
        print("Advice: Seek immediate medical attention. Speak to a healthcare provider for assistance.")
else:
    print("Please input valid values for weight and height.")
```
## 7. Final Output:
The program prints the user's BMI value and provides the corresponding BMI category, health risk, and advice.

By following this flow, the program guides users through calculating their BMI, understanding their body mass status, and offering advice for maintaining or improving their health.


## Author

This project was created and maintained by [Pankaj Singh Bisht](https://github.com/pbisht2105).

You can contact me at: [pbisht2105@gmail.com](mailto:pbisht2105@gmail.com).
