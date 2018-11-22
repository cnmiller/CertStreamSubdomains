# CertStream Subdomains
Subdomains collected from certificate transparency logs

## Command to convert raw cerstream logs (certs.txt) to cleaned subdomain list (certs_clean.txt)
cat certs.txt | gsed -r "s/\x1B\[([0-9]{1,2}(;[0-9]{1,2})?)?[mGK]//g" | cut -d" " -f4 | rev | cut -d"." -f2- | rev | sed '/*/d' | sed '/www./d' | sed '/.com/d' > certs_clean.txt #gsed if on mac (install with brew install gnu-sed, sed otherwise)
