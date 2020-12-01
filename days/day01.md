- What is the name of the cookie used for authentication?

```auth```
```
Can be found by looking into the storage of browser
```

What is the name of the cookie used for authentication?

```
hexadecimal
```

Having decoded the cookie, what format is the data stored in?

```
json
```
```
bytes.fromhex('7b22636f6d70616e79223a22546865204265737420466573746976616c20436f6d70616e79222c2022757365726e616d65223a226161616161227d').decode('utf-8')
'{"company":"The Best Festival Company", "username":"aaaaa"}'
```
What is the value of Santa's cookie?

```
7b22636f6d70616e79223a22546865204265737420466573746976616c20436f6d70616e79222c2022757365726e616d65223a2273616e7461227d
```
```
>>> '{"company":"The Best Festival Company", "username":"aaaaa"}'.encode('utf-8').hex()
'7b22636f6d70616e79223a22546865204265737420466573746976616c20436f6d70616e79222c2022757365726e616d65223a226161616161227d'
```
What is the flag you're given when the line is fully active?

```
THM{MjY0Yzg5NTJmY2Q1NzM1NjBmZWFhYmQy}
```
```
Activate all the toggle buttons.
```
