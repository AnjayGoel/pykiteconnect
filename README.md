# Open Kite Connect

Fork of the official [Python client](https://github.com/zerodha/pykiteconnect), allowing free access to the api.

### How to use:

Apart from authorization, works same as the official client.

### Example

**HTTP**

```python
import logging
import os
from kiteconnect import KiteConnect
from dotenv import load_dotenv

load_dotenv()

logging.basicConfig(level=logging.DEBUG)

kite = KiteConnect()
kite.login(os.getenv("USER_ID"), os.getenv("USER_PASSWORD"), os.getenv("USER_PIN"))
print(kite.profile())
kite.logout()

```

**WebSocket**

```python
kite = KiteConnect(debug=True)
kite.login(os.getenv("USER_ID"), os.getenv("USER_PASSWORD"), os.getenv("USER_PIN"))
kws = KiteTicker(kite.access_token)
# Full code in examples folder
```

For more examples, see examples folder

### How does it work?

Uses the web-app endpoints to generate an access token.