# cURL-error-60-SSL-certificate-problem-certificate-has-expired
We running 2 envoirment on wafaicloud / jelastic (backend.abc.com &amp; frontend.abc.com). For that application, we used a Cloudflare SSL Certificate. That certificate expiration date at 2035 by Cloudflare. But today, we got an error 

**Output**
```
Error executing "PutObject" on "https://storage.mydomain.com./project/xxxxxxxxx.png"; AWS HTTP error: cURL error 60: SSL certificate problem: certificate has expired (see https://curl.haxx.se/libcurl/c/libcurl-errors.html) for https://storage.mydomain.com./project/xxxxxxxxx.png
```
**Error**
```
cURL error 60: SSL certificate problem: certificate has expired (see https://curl.haxx.se/libcurl/c/libcurl-errors.html) for https://storage.mydomain.com./project/
```
# solution-1
To fix the problem, remove the expired root certificate from your domain certificate.

1- Go to https://whatsmychaincert.com

2- Test Your Server

3- If they confirm you you have an expired root certificate, download and use the .crt without this certificate.

# solution-2
**Recommended:** https://youtu.be/9LpQlKJ1HyE

**follow this youtube link and change or edit the settings below**:
![x7a42](https://user-images.githubusercontent.com/71556060/161909354-bf26e87f-a9f3-4707-b855-57ee90f61416.png)

**also follow this file formate too**
server key = A server key is a private encryption/decryption key used by the server.(myfile.pem.key)

Intermediate Certificate (CA) = Certificate Authority (CA) is an entity that issues digital certificates which will verify the ownership of a public key by the named subject of the certificate.(myfile.pem)

Domain Certificate = A domain certificate is an electronic document that is given by the Certification Authority which checks the permission of the applicant to use a specific domain name.(myfile.pem)
