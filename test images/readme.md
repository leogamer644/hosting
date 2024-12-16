# test performed
### Performance tests

These tests were performed with `ab`, which is a benchmarking tool Apache has. This shows you how many requests per second your Apache installation is capable of serving.


<details>
    <summary style="font-size: 18px"><b>No compression tests</b></summary><br/>

### Parameters:

* `-k` : Enable the HTTP KeepAlive  feature,  i.e.,  perform  multiple  requests within one HTTP session. Default is no KeepAlive.

* `-c` (concurrency): Number of multiple requests to perform at a time Default is one request at a time.

* `-n` (requests): Number of requests to perform for the benchmarking session. The default is to just perform a single request which usually leads  to  non-repre‐ sentative benchmarking results.



### 100 users and 1000 requests


<details>
    <summary><b>Index page with TLS1.3</b></summary><br/>

Extra Parameters:

* `-f` (protocol): Specify SSL/TLS protocol (SSL2, TLS1, TLS1.1, TLS1.2, TLS1.3 or ALL)


```bash
ab -k -f TLS1.3 -c 100 -n 1000 https://leogamer644.com
```
</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 100 -n 1000 https://leogamer644.com/files/logo.png
```

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
    <summary><b>Index page with TLS1.3</b></summary><br/>

```bash
ab -k -f TLS1.3 -c 1000 -n 10000 https://leogamer644.com/
```

</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 1000 -n 10000 https://leogamer644.com/files/logo.png
```


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
    <summary><b>Index page with TLS1.3</b></summary><br/>

```bash
ab -k -f TLS1.3 -c 100 -n 1000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/
```


</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 100 -n 1000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/files/logo.png
```


</details>

<details>
    <summary><b>Admin page</b></summary><br/>

```bash
ab -k -c 100 -n 1000 -A admin:asir -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/admin/
```


</details>



### 1000 users and 10000 requests

<details>
    <summary><b>Index page with TLS1.3</b></summary><br/>

```bash
ab -k -f TLS1.3 -c 1000 -n 10000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/
```


</details>

<details>
    <summary><b>Logo.png image (301KB)</b></summary><br/>

```bash
ab -k -c 1000 -n 10000 -H "Accept-Encoding: gzip, deflate" https://leogamer644.com/logo.png
```

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

.


<br/>

---

<br/>
