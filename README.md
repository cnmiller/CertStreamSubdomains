# CertStream Subdomains
Subdomains collected from certificate transparency logs

## Command to convert raw cerstream logs (certs.txt) to cleaned subdomain list (certs_clean.txt)
```
cat certs.txt | gsed -r "s/[[:cntrl:]]\[[0-9]{1,3}m//g" | cut -d" " -f4 | rev | cut -d"." -f2- | rev | sed '/*/d' | sed '/www./d' | sed '/.com/d' > certs_clean.txt
```
