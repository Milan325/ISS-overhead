# ISS-overhead
This program is a tool for checking if the International Space Station is near the user specified longitude and latitude at night, and sends an email to the user if it is.

## Use
This script is mate to run in a backgroung, and to check the position of the ISS every 60 seconds, and compare it with user's given position, and send an email to user if it is nighttime and the ISS is closer than 5 degrees longitude and latitude from the user.

## Modules and functions
The program uses `requests` module get and use data from [Sunrise-Sunset](https://api.sunrise-sunset.org/json) API and [Open Notify](http://api.open-notify.org/iss-now.json) API, `datetime` module to check if it is nighttime at the specified location, `smtplib` module for sending emails and `time` module to make `while` loop running at pace of 60 seconds. 

## Program engine
The program engine is a `while` loop that runs every 60 seconds, and checks if `is_iss_overhead()` and `is_night` functions return True. If both functions are Ture, then an email is sent using:
```python
connection = smtplib.SMTP("__YOUR_SMTP_ADDRESS_HERE___")
        connection.starttls()
        connection.login(MY_EMAIL, MY_PASSWORD)
        connection.sendmail(
            from_addr=MY_EMAIL,
            to_addrs=MY_EMAIL,
            msg="Subject:Look Up👆\n\nThe ISS is above you in the sky."
        )
```

## Running the program
This game is intended to be run by Python IDE or other Python interpeter. 
To install Python 3 see [Tutorials Point page](https://www.tutorialspoint.com/how-to-install-python-in-windows).
