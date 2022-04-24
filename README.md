# MTA Bus Alerts

This project aims to let people know when the bus is nearby. The user picks a bus route, a bus stop, and
a number of minutes or number of stops, and this app will send them an email when their bus is near the
bus stop (within the number of minutes or stops the user set).

To run this project:
1. Clone it
2. Create a virtual environment

        python3 -m venv venv

3. Activate the virtual environment

        source venv/bin/activate

4. Install all package requirements

        pip install -r requirements.txt

5. Start flask app

        flask run
        
6. Set up alert. To do this, send a POST request to the /alert endpoint with the following keys:
    * busStopID (required): the six digit code identifying the bus stop
    * busLineID (required): official name of the bus route you're tracking (e.g. MTA NYCT_Q54 for the Q54)
    * email (required): the email address where you want to receive the alert
    * units (optional): either 'minutes' or 'bus stops'. Bus stops by default.
    * number (optional): the number of minutes/bus stops before a bus arrives when you want to receive the alert. 5 by default.
