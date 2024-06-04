# calendar-project-python-easy
This is a ‘Calendar’ based program. It has been created keeping in mind the basic functions of a calendar program. It involves basic features that the user many require frequently. This program is built with the basic idea and knowledge of calendars and allows the user to carry a limited set of functions. 

Date Management Tool

This Python script offers various functionalities for managing dates:

Calendar Printing (2021-2031): Prints the calendar for a specified month within the years 2021 to 2031.
Date Validation: Checks whether a given date (day, month, year) is valid according to the Gregorian calendar.
Day Name Calculation (1600-1999): Calculates the day of the week (e.g., Monday, Tuesday) for a particular date between the years 1600 and 1999.
Festival Listing (2022): Retrieves a list of festivals for a chosen month in the year 2022 (data is limited to this year).
Date After n Days: Determines the date that results from adding a specified number of days to a given date.
Usage

Save the code as a Python file (e.g., date_manager.py).
Run the script from your terminal using the following command:
Bash
python date_manager.py
Use code with caution.
content_copy
The script will present a menu with the following options:

Print calendar for one month (only for 2021 to 2031)
Check whether the date is valid or not
Get the day name of a particular date (only for 1600 to 1999)
Get the festivals in any particular month (only for 2022)
Date after n days
Enter the corresponding number to select the desired functionality.

Follow the on-screen prompts to provide any additional information required (e.g., year, month, date, number of days).

Notes

The calendar printing function relies on pre-defined lists containing the starting day of the week for each year from 2021 to 2031.
For a more robust solution, consider employing a more comprehensive calendar generation algorithm.
The day name calculation for dates between 1600 and 1999 uses an algorithmic approach.
The festival data is restricted to the year 2022.

for s in range(100000):
    print("Read the options and choose any one:-")
    print("1. Print calendar for one month (only for 2021 to 2031)")
    print("2. Check whether the date is valid or not")
    print("3. Get the day name of a particular date (only for 1600 to 1999)")
    print("4. Get the festivals in any particular month (only for 2022)")
    print("5. Date after n days")

    option = int(input("Type the option:-"))
    
    if option >= 6 or option <= 0:
        print("Invalid option entered")
        continue
    
    if option == 1:
        while True:
            print("You want to print calendar")
            year21 = ('Friday', 'Monday', 'Monday', 'Thursday', 'Saturday', 'Tuesday', 'Thursday', 'Sunday', 'Wednesday', 'Friday', 'Monday', 'Wednesday')
            year22 = ('Saturday', 'Tuesday', 'Tuesday', 'Friday', 'Sunday', 'Wednesday', 'Friday', 'Monday', 'Thursday', 'Saturday', 'Tuesday', 'Thursday')
            year23 = ('Sunday', 'Wednesday', 'Wednesday', 'Saturday', 'Monday', 'Thursday', 'Saturday', 'Tuesday', 'Friday', 'Sunday', 'Wednesday', 'Friday')
            year24 = ('Monday', 'Thursday', 'Friday', 'Monday', 'Wednesday', 'Saturday', 'Monday', 'Thursday', 'Sunday', 'Tuesday', 'Friday', 'Sunday')
            year25 = ('Wednesday', 'Saturday', 'Saturday', 'Tuesday', 'Thursday', 'Sunday', 'Tuesday', 'Friday', 'Monday', 'Wednesday', 'Saturday', 'Monday')
            year26 = ('Thursday', 'Sunday', 'Sunday', 'Wednesday', 'Friday', 'Monday', 'Wednesday', 'Saturday', 'Tuesday', 'Thursday', 'Sunday', 'Tuesday')
            year27 = ('Friday', 'Monday', 'Monday', 'Thursday', 'Saturday', 'Tuesday', 'Thursday', 'Sunday', 'Wednesday', 'Friday', 'Monday', 'Wednesday')
            year28 = ('Saturday', 'Tuesday', 'Wednesday', 'Saturday', 'Monday', 'Thursday', 'Saturday', 'Tuesday', 'Friday', 'Sunday', 'Wednesday', 'Friday')
            year29 = ('Monday', 'Thursday', 'Thursday', 'Sunday', 'Tuesday', 'Friday', 'Sunday', 'Wednesday', 'Saturday', 'Monday', 'Thursday', 'Saturday')
            year30 = ('Tuesday', 'Friday', 'Friday', 'Monday', 'Wednesday', 'Saturday', 'Monday', 'Thursday', 'Sunday', 'Tuesday', 'Friday', 'Sunday')
            year31 = ('Wednesday', 'Saturday', 'Saturday', 'Tuesday', 'Thursday', 'Sunday', 'Tuesday', 'Friday', 'Monday', 'Wednesday', 'Saturday', 'Monday')

            year = int(input("Calendar of which year you want to print?"))
            mm = int(input("Calendar of which month you want to print?"))

            if year == 2021:
                start_day = year21[mm - 1]
            elif year == 2022:
                start_day = year22[mm - 1]
            elif year == 2023:
                start_day = year23[mm - 1]
            elif year == 2024:
                start_day = year24[mm - 1]
            elif year == 2025:
                start_day = year25[mm - 1]
            elif year == 2026:
                start_day = year26[mm - 1]
            elif year == 2027:
                start_day = year27[mm - 1]
            elif year == 2028:
                start_day = year28[mm - 1]
            elif year == 2029:
                start_day = year29[mm - 1]
            elif year == 2030:
                start_day = year30[mm - 1]
            elif year == 2031:
                start_day = year31[mm - 1]
            else:
                print("Invalid year entered")
                continue

            days_in_week = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']
            startno = days_in_week.index(start_day)

            print("Sun Mon Tue Wed Thu Fri Sat")
            if mm in [4, 6, 9, 11]:
                days = 30
            elif mm == 2:
                if year in [2024, 2028]:
                    days = 29
                else:
                    days = 28
            else:
                days = 31

            for j in range(startno):
                print("    ", end=" ")
            for i in range(1, days + 1):
                print(f"{i:3}", end=" ")
                if (i + startno) % 7 == 0:
                    print()
            print("\nWant to continue? y/n")
            I1 = input("Enter:-")
            if I1.lower() == 'n':
                break

    if option == 2:
        while True:
            print("You want to check date validity")
            dd = int(input("Enter the date:-"))
            mm = int(input("Enter the month:-"))
            yy = int(input("Enter the year:-"))
            print(f"Your entered date is: {dd}.{mm}.{yy}")
            
            if (mm in [4, 6, 9, 11] and dd > 30) or (mm == 2 and yy % 4 == 0 and dd > 29) or (mm == 2 and yy % 4 != 0 and dd > 28) or (mm not in range(1, 13)) or (dd not in range(1, 32)) or (yy > 9999 or yy < 0):
                print("Invalid date")
            else:
                months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]
                print(f"Your entered date is valid: {dd} {months[mm-1]}, {yy}")

            print("Want to continue? y/n")
            I2 = input("Enter:-")
            if I2.lower() == 'n':
                break

    if option == 3:
        while True:
            print("You want to get the day name of a particular date")
            d = int(input("Enter the date:-"))
            m = int(input("Enter month no:-"))
            f = int(input("Enter first two digits of the year:-"))
            l = int(input("Enter last two digits of the year:-"))

            if m == 1:
                mno = 1
            elif m == 2:
                mno = 4
            elif m == 3:
                mno = 4
            elif m == 4:
                mno = 0
            elif m == 5:
                mno = 2
            elif m == 6:
                mno = 5
            elif m == 7:
                mno = 0
            elif m == 8:
                mno = 3
            elif m == 9:
                mno = 6
            elif m == 10:
                mno = 1
            elif m == 11:
                mno = 4
            elif m == 12:
                mno = 6
            else:
                print("Invalid month entered")
                continue

            if f == 16:
                fno = 6
            elif f == 17:
                fno = 4
            elif f == 18:
                fno = 2
            elif f == 19:
                fno = 0
            else:
                print("Invalid century entered")
                continue

            dd = l // 4
            sum = d + mno + fno + l + dd
            sum = sum % 7

            weekdays = ["Saturday", "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday"]
            print(weekdays[sum])

            print("Want to continue? y/n")
            I3 = input("Enter:-")
            if I3.lower() == 'n':
                break

    if option == 4:
        while True:
            print("You want to print festivals")
            fest = int(input("Enter the month no. for festivals in 2022:-"))

            festivals = {
                1: ["New Year- 1st January Saturday", "Lohri- 13th January Thursday", "Makar Sankranti- 14th January Friday", "Subhash Chandra Bose Jayanti- 23rd January Sunday"],
                2: ["Basant Panchmi- 5th February Saturday"],
                3: ["Mahashivratri- 1st March Tuesday", "Holika Dahan- 17th March Thursday", "Holi- 18th March Friday"],
                4: ["Ram Navami- 10th April Sunday", "Baisakhi, Ambedkar Jayanti- 14th April Thursday", "Good Friday- 15th April Friday", "Hanuman Jayanti- 16th April Saturday"],
                5: ["Buddha Purnima- 16th May Monday"],
                6: ["No main festival in June"],
                7: ["Bakrid- 10th July Sunday", "Guru Purnima- 13th July Wednesday"],
                8: ["Raksha Bandhan- 11th August Thursday", "Independence Day- 15th August Monday", "Janmashtmi- 19th August Friday", "Ganesh Chaturthi- 31st August Wednesday"],
                9: ["Gandhi Jayanti- 2nd October Sunday", "Dussehra- 5th October Wednesday"],
                10: ["Karwa Chauth- 13th October Thursday", "Ahoi Ashtami- 17th October Monday", "Diwali- 24th October Monday", "Bhai Dooj- 26th October Wednesday"],
                11: ["Guru Nanak Jayanti- 8th November Tuesday"],
                12: ["Christmas- 25th December Sunday"]
            }

            if fest in festivals:
                for event in festivals[fest]:
                    print(event)
            else:
                print("Invalid month entered")

            print("Want to continue? y/n")
            I4 = input("Enter:-")
            if I4.lower() == 'n':
                break

    if option == 5:
        while True:
            print("You want to know the date after n days")
            d = int(input("Enter the date:-"))
            m = int(input("Enter month no:-"))
            y = int(input("Enter the year:-"))
            ndays = int(input("Enter no of days to be added:-"))

            def is_leap(year):
                return year % 4 == 0 and (year % 100 != 0 or year % 400 == 0)

            days_in_months = [31, 29 if is_leap(y) else 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]

            while ndays > 0:
                if ndays + d <= days_in_months[m - 1]:
                    d += ndays
                    ndays = 0
                else:
                    ndays -= days_in_months[m - 1] - d + 1
                    d = 1
                    m += 1
                    if m > 12:
                        m = 1
                        y += 1
                        days_in_months[1] = 29 if is_leap(y) else 28

            months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]
            print(f"The date after adding {ndays} days is: {d} {months[m-1]}, {y}")

            print("Want to continue? y/n")
            I5 = input("Enter:-")
            if I5.lower() == 'n':
                break
