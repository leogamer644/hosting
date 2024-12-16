# test performed
### Performance tests

These tests were performed with `ab`, which is a benchmarking tool Apache has. This shows you how many requests per second your Apache installation is capable of serving.
I will not show admin page tests, as they will more than likely fail due to the way it's implemented

<details>
    <summary style="font-size: 18px"><b>No compression tests</b></summary><br/>

### Parameters:

* `-k` : Enable the HTTP KeepAlive  feature,  i.e.,  perform  multiple  requests within one HTTP session. Default is no KeepAlive.

* `-c` (concurrency): Number of multiple requests to perform at a time Default is one request at a time.

* `-n` (requests): Number of requests to perform for the benchmarking session. The default is to just perform a single request which usually leads  to  non-repre‐ sentative benchmarking results.



### 100 users and 1000 requests


<details>
    <summary><b>Index page with TLS1.2</b></summary><br/>

Extra Parameters:

* `-f` (protocol): Specify SSL/TLS protocol (SSL2, TLS1, TLS1.1, TLS1.2, TLS1.3 or ALL)


```bash
ab -k -f TLS1.2 -c 100 -n 1000 https://leogamer644.com
```
<img width="334" alt="Screenshot_29" src="https://github.com/user-attachments/assets/32eb8566-688e-492f-b830-dbb52663030a" />

</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 100 -n 1000 https://leogamer644.com/files/logo.png
```
![image](https://github.com/user-attachments/assets/c1ab08e2-e753-49d2-a64e-a4ea218c6593)

</details>

<details>
    <summary><b>Admin page</b></summary><br/>

It cant be done as I use php for authentication... but you can test the failure...

Extra Parameters:

* `-A` (attribute): Add Basic WWW Authentication, the attributes are a colon separated username and password.

```bash
ab -k -c 100 -n 1000 -A admin:asir https://leogamer644.com/admin/
```

</details>




### 1000 users and 10000 requests

<details>
    <summary><b>Index page with TLS1.2</b></summary><br/>

```bash
ab -k -f TLS1.2 -c 1000 -n 10000 https://leogamer644.com/
```
<img width="333" alt="Screenshot_30" src="https://github.com/user-attachments/assets/09492313-da9a-48b5-bf9f-2fd8d12075b1" />

</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 1000 -n 10000 https://leogamer644.com/files/logo.png
```
<img width="336" alt="Screenshot_32" src="https://github.com/user-attachments/assets/854fcf72-490d-4ee1-a781-0557dfc9609d" />


</details>

<details>
    <summary><b>Admin page</b></summary><br/>

```bash
ab -k -c 1000 -n 10000 -A admin:asir https://leogamer644.com/admin/
```


</details>

<br/>

---

<br/>

</details>






<details>
    <summary style="font-size: 18px"><b>Compression tests</b></summary><br/>

### Parameters:

* `-k` : Enable the HTTP KeepAlive  feature,  i.e.,  perform  multiple  requests within one HTTP session. Default is no KeepAlive.

* `-c` (concurrency): Number of multiple requests to perform at a time Default is one request at a time.

* `-n` (requests): Number of requests to perform for the benchmarking session. The default is to just perform a single request which usually leads  to  non-repre‐ sentative benchmarking results.

* `-H` (custom-header): Append extra headers to the request. The argument is typically  in  the form  of  a valid header line, containing a colon-separated field-value pair (i.e., "Accept-Encoding: zip/zop;8bit" or "Accept-Encoding: gzip, deflate")



### 100 users and 1000 requests

<details>
    <summary><b>Index page with TLS1.2</b></summary><br/>

```bash
ab -k -f TLS1.2 -c 100 -n 1000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/
```
![image](https://github.com/user-attachments/assets/9346998f-8942-459e-b04d-964f3c9f2dd5)

</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 100 -n 1000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/files/logo.png
```
![image](https://github.com/user-attachments/assets/597c9910-ca41-42d5-81d8-e98990f4631b)


</details>

<details>
    <summary><b>Admin page</b></summary><br/>

```bash
ab -k -c 100 -n 1000 -A admin:asir -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/admin/
```


</details>



### 1000 users and 10000 requests

<details>
    <summary><b>Index page with TLS1.2</b></summary><br/>

```bash
ab -k -f TLS1.2 -c 1000 -n 10000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/
```
![image](https://github.com/user-attachments/assets/336b852f-03fd-4089-bf35-f742c9bb027e)


</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 1000 -n 10000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/logo.png
```
![image](https://github.com/user-attachments/assets/5c8c7b18-dc22-42ae-8256-8c87e91779ec)

</details>

<details>
    <summary><b>Admin page</b></summary><br/>

```bash
ab -k -c 1000 -n 10000 -A admin:asir -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/admin/
```

</details>

<br/>

---

<br/>

</details>


### Conclusion

It's very harsh on the server to request 1000 users at the same time, even more so when I download a file. It actually crashed the network interface in my ubuntu host... so I had to restart it, that's why there was 1 attempt only that went okay at logo download with 1000 users and compression enabled...


<br/>

---

<br/>
