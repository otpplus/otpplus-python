# otpplus-python
OTPPlus Python SDK - Send Free SMS OTPs from your application. Register your account at [otp.plus/registration](http://otp.plus/registration), get your access key and send 30 SMSs free every month! No credit card required! Send an email to [sales@otp.plus](mailto:sales@otp.plus) for more!

## How to install using pip
Coming Soon!

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

## API Documentation
Check `docs/index.html` for complete API documentation.

## License
The MIT License (MIT)

Copyright (c) 2023 otp.plus

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.