# gwmailpy
A simple api wrapper for (temp-mail) mail.gw.

## Installation

```
pip install gwmailpy
```

## Usage

```py
from gwmailpy import GwApi
import time

# Initialize class
api = GwApi(proxy='here', timeout=30)

# Load mail
email = api.load_mail()
print(f'Your temp-mail: {email}')

while True:
    time.sleep(5)
    for mail in api.load_inbox():
        content = api.get_message_value(mail['id'])
        print(f'[*] A message from: {mail["from"]["address"]}\n{content}')
````
