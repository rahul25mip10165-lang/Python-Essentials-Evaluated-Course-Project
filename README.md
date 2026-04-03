🔐 Password Strength Checker & Generator
A lightweight Python utility that evaluates password strength and generates cryptographically secure passwords using Python's built-in secrets module.

Features

Password Strength Checker — Rates any password as Weak, Medium, or Strong based on common security criteria
Secure Password Generator — Generates random passwords that are guaranteed to meet Strong criteria
Zero dependencies — Uses only Python standard library modules (re, string, secrets)


How It Works
Strength Criteria
A password is evaluated against 5 criteria:
CriteriaDescriptionLengthAt least 8 charactersDigitContains at least one number (0–9)UppercaseContains at least one uppercase letter (A–Z)LowercaseContains at least one lowercase letter (a–z)SymbolContains at least one special character or underscore
Scoring:
Criteria MetRating5 out of 5✅ Strong3 – 4 out of 5⚠️ Medium0 – 2 out of 5❌ Weak

Getting Started
Prerequisites

Python 3.6 or higher

No additional packages are required.
Installation
Clone the repository:
bashgit clone https://github.com/your-username/password-checker.git
cd password-checker
Usage
Run the script directly:
bashpython password_checker.py
You will be prompted to enter a password. The script will:

Rate the strength of your password
Suggest a strong randomly generated password

Example output:
Enter a password to check: hello123

'hello123' is: Medium

Here is a suggested strong password:
Suggestion: gT#7kLmQ2@rXpZ
Strength check for suggestion: Strong

API Reference
You can also import the functions into your own scripts:
pythonfrom password_checker import check_password_strength, generate_strong_password

# Check strength
strength = check_password_strength("MyP@ssw0rd!")
print(strength)  # Strong

# Generate a strong password (default length: 12)
password = generate_strong_password(length=16)
print(password)
check_password_strength(password)
ParameterTypeDescriptionpasswordstrThe password string to evaluate
Returns: "Weak", "Medium", or "Strong"

generate_strong_password(length=12)
ParameterTypeDefaultDescriptionlengthint12Desired length of the generated password
Returns: A str password that meets all 5 strength criteria.

⚠️ Note: Passing a length below 8 may cause an infinite loop since short passwords can never meet all strength criteria. A minimum of 8 is strongly recommended.


Security Notes

Password generation uses Python's secrets module, which is designed for cryptographic use — unlike random.
The character pool includes uppercase, lowercase, digits, and string.punctuation.
Generated passwords are validated against the strength checker before being returned.


Project Structure
password-checker/
│
├── password_checker.py   # Main script
└── README.md             # Documentation

License
This project is open source and available under the MIT License.
