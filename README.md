import re

def check_pas(password):
    lenght_9=re.compile(r'^.{8,}$')
    upper_r=re.compile(r'[A-Z]')
    lower_r=re.compile(r'[a-z]')
    digit_r=re.compile(r'[\d]')
    special_r=re.compile(r'[\w]')

    lenght_check=lenght_9.search(password)
    upper_check=upper_r.search(password)
    lower_check=lower_r.search(password)
    digit_check=digit_r.search(password)
    special_check=special_r.search(password)

    if lenght_check and upper_check and lower_check and digit_check and special_check:
        return True
    else:
        return False

with open('password.txt') as f:
    for password in f:
        password=password.strip()
        if check_pas(password):
            print(f"valid password{password}")
        else:
            print(f"not valid{password}")

            

<!---
sujal511/sujal511 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
