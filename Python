# Constants for fluid compartments (in liters)
TBW_MALE = 0.6
TBW_FEMALE = 0.5
ICF_PERCENT = 0.4
ECF_PERCENT = 0.6

# Function to calculate body fluid volumes
def calculate_body_fluid_volume(weight, height, age, gender):
    # Calculate total body water (TBW)
    if gender.lower() == 'male':
        tbw = TBW_MALE * weight
    elif gender.lower() == 'female':
        tbw = TBW_FEMALE * weight
    else:
        raise ValueError("Invalid gender specified. Please choose 'male' or 'female'.")

    # Calculate intracellular fluid (ICF) and extracellular fluid (ECF)
    icf = ICF_PERCENT * tbw
    ecf = ECF_PERCENT * tbw

    # Calculate plasma volume
    if gender.lower() == 'male':
        plasma_volume = 0.045 * tbw
    elif gender.lower() == 'female':
        plasma_volume = 0.055 * tbw

    # Calculate blood volume
    blood_volume = plasma_volume / 0.45

    # Calculate total fluid volume
    total_fluid_volume = tbw + blood_volume

    return {
        'Total Body Water': tbw,
        'Intracellular Fluid': icf,
        'Extracellular Fluid': ecf,
        'Plasma Volume': plasma_volume,
        'Blood Volume': blood_volume,
        'Total Fluid Volume': total_fluid_volume
    }

# Example usage
weight = float(input("Enter weight in kg: "))
height = float(input("Enter height in cm: "))
age = int(input("Enter age in years: "))
gender = input("Enter gender (male/female): ")

fluid_volumes = calculate_body_fluid_volume(weight, height, age, gender)
print("\nBody Fluid Volumes:")
for compartment, volume in fluid_volumes.items():
    print(f"{compartment}: {volume} liters")
