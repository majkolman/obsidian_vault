Building docker:
`docker build -t <name> .`
`docker run -ti -p <port:port> --rm <name>`

## introweb:
### server.py:
```
import flask

import subprocess

  

app = flask.Flask(__name__)

  

@app.route('/', methods=['GET', 'POST'])

def index():

    response = ""

    if flask.request.method == 'POST':

        host = flask.request.form['host'].strip()

        if not host:

            response = "No host provided."

        else:

            try:

                result = subprocess.run(f"ping -c 4 '{host}'", shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE, text=True)

                if result.returncode == 0:

                    response = f"{result.stdout}"

                else:

                    response = f"An error occurred while pinging"

            except Exception:

                response = f"An error occurred"

    return flask.render_template_string('''

        <h1>Welcome to PAAS (Ping As A Service)</h1>

        <form action="/" method="post">

            <input type="text" name="host" placeholder="Enter host to ping" required>

            <button type="submit">Ping</button>

        </form>

        <pre>{{ response }}</pre>

    ''', response=response)

  

if __name__ == '__main__':

    app.run(host='0.0.0.0', port=8000)
```

## intronetcat
### server.py
```
import random

import os

  

print("Welcome to the math quiz! How fast are you?")

  

for i in range(25):

    a = random.randint(1, 100)

    b = random.randint(1, 100)

    answer = a + b

    user_input = input(f"{a} + {b} = ")

    user_input = user_input.strip()

    try:

        if int(user_input) != answer:

            print("Wrong answer! Good bye.")

            break

    except ValueError:

        print("Invalid input! Good bye.")

        break

else:

    print(os.environ.get("FLAG", "FLAG{fake_flag_for_testing}"))
```

### sol.py
```
from pwn import *

  

#p = process(["python3", "server.py"])

#ncat --ssl inst-y07fsdv6eb.tls.vuln.si 443

p = remote("inst-y07fsdv6eb.tls.vuln.si", 443, ssl=True)

p.recvline()

  

for i in range(25):

    line = p.recvuntil(b" = ")

    lines = line.split(b" ")

  

    ans = int(lines[0]) + int(lines[2])

    p.sendline(str(ans).encode())

  

p.interactive()
```
