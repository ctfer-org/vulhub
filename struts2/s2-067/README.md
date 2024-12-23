# Struts2 S2-067 Remote Code Execution (CVE-2024-53677)


An attacker can manipulate file upload params to enable paths traversal and under some circumstances this can lead to uploading a malicious file which can be used to perform Remote Code Execution.

Note: applications not using FileUploadInterceptor are safe.


```SHELL

docker-compose up -d

```