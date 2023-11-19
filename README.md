# otpplus-python
OTPPlus Python SDK

## How to install from source code
Create a virtual environment (optional) and run the following command:
~~~
pip install .
~~~
or for editable mode:
~~~
pip install -e .
~~~

## Example
~~~
from otpplus import client

# Create a OTPPlus Client Object
obj = client.OTPPlus('<ACCESS-KEY>', 'uat')

# Send an auto-generated OTP
# otp_id, err = obj.send_otp('4084446640')

# Send Custom OTP
otp_id, err = obj.send_otp('4084446640', 23456)

# Check OTP send status
if err is None:
  print('OTP Sent. ID: ' + otp_id)
else:
  print('Could not send OTP: ' + err)
  exit(1)

# Verify OTP
verified, err = obj.verify_otp(otp_id, 23456)
if verified:
  print('OTP verified!')
else:
  print('Could not verify OTP: ' + err)
~~~