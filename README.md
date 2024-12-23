# Age-Calculator-
from datetime import datetime

def calculate_age(birthdate):
    # Get today's date
    today = datetime.today()
    
    # Calculate the difference in years
    age = today.year - birthdate.year
    
    # Adjust age if birthday hasn't occurred yet this year
    if today.month < birthdate.month or (today.month == birthdate.month and today.day < birthdate.day):
        age -= 1
    
    return age

# Input for birthdate
birth_date_input = input("Enter your birthdate (YYYY-MM-DD): ")

# Convert input string to a datetime object
birth_date = datetime.strptime(birth_date_input, "%Y-%m-%d")

# Calculate and display age
age = calculate_age(birth_date)
print(f"Your age is {age} years.")
