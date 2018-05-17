DVWA Zap Scan POC


Requires:

You need to set up two docker instances for this to run:

ZAP Proxy:

docker run --name zaproxy -u zap -p 8080:8080 -i owasp/zap2docker-stable zap.sh -daemon -host 0.0.0.0 -port 8080 -config api.addrs.addr.name=.* -config api.addrs.addr.regex=true -config api.disablekey=true

DVWA:

docker run -d -p 7080:80 -p 3306:3306 -e MYSQL_PASS="mypass" infoslack/dvwa

Execution:

mvn verify

