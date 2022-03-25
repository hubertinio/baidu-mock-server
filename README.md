# Baidu Mock Server

https://www.mock-server.com/#what-is-mockserver

## What is Baidu?

Help with implementations of submit URLs to Baidu.

https://chineseseoshifu.com/kb/submit-urls-to-baidu/

---

## Requirements 

* docker 
* docker-compose

---

## Configuration

### Mock Server Configuration

[Manual](https://www.mock-server.com/mock_server/configuration_properties.html)

Config: `./config/mockserver.properties`

### Related project on host

Add to `/etc/hosts`

```bash
127.0.0.1 data.baidu.loc
```

### Related project on docker

You can access host services using the IP address of the docker0 interface

```bash
ip addr show docker0
docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 00:00:00:00:00:00 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
```

Set The Mock As Env Var

```bash
BAIDU_API_HOST=http://172.17.0.1:18080/
```

## Web GUI

[Manual](https://www.mock-server.com/mock_server/mockserver_ui.html)

[127.0.0.1 Dashboard](http://localhost:18080/mockserver/dashboard)

---

## Expectations

[Manual](https://www.mock-server.com/mock_server/initializing_expectations.html#expectation_initializer_json)

Init expectations are here: `./config/initializerJson.json`

---

## Troubleshooting

#### Can't connect to remote host (127.0.0.1): Connection refused 

https://tjtelan.com/blog/how-to-link-multiple-docker-compose-via-network/

---

## Appendix

[Testing RESTful Web Services with PHP Storm](https://www.jetbrains.com/help/phpstorm/http-client-in-product-code-editor.html)
