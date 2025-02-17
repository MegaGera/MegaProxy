# MegaProxy


**MegaProxy** is a service within [**Mega microservices architecture**](https://github.com/MegaGera/Mega).

*MegaProxy* is the proxy that acts as the entry point of *Mega* that redirects the requests and connections to the different *Mega* applications and services.


## Table of Contents

- [Service Description](#service-description)
- [Part of Mega](#part-of-mega)
- [Build & Deploy](#build--deploy)
- [License](#license)
- [Contact & Collaborate](#contact--collaborate)

## Service Description

*MegaProxy* is the microservice that **handles the requests to `*megagera.com`**. The service is built with [Nginx](https://nginx.org/en/). It exposes the only port to the internet from the inside of *Mega* microservices architecture.

It's deployed by a **Docker container** in *Mega*, so it's the only output interface of the *Mega* docker network.

Most of the **routes are validated with *MegaAuth*** to see if the request is donde by a logged user. If it's corrected it forwards the connection to the required service, if not it redirects to *MegaAuth* login page.

All the connections are by **HTTPS** and validated with certificates.

All the *MegaProxy* code is in [`megaproxy.conf`](megaproxy.conf)

Already running in production in [https://megagera.com](https://megagera.com).

Only the API Servers of *MegaGoal* and *MegaMedia* are not validated by *MegaAuth* in *MegaProxy* because they handle the validation of permissions by their owns.

## Part of Mega

*MegaProxy* is part of the larger [**Mega**](https://github.com/MegaGera/Mega) project, a collection of web applications built with a **microservices architecture**.

[**Mega**](https://github.com/MegaGera/Mega) includes other services such as an [Authentication (*MegaAuth*)](https://github.com/MegaGera/MegaAuth) service, a [Footbal App (*MegaGoal*)](https://github.com/MegaGera/MegaGoal), and other Web Applications ([*MegaMedia*](https://github.com/MegaGera/MegaMedia), [*MegaHome*](https://github.com/MegaGera/MegaHome), [*MegaDocu*](https://docusaurus.io/))

## Build & Deploy

[`docker-compose.yml`](docker-compose.yml) file manages the image and handle it easily within the *Mega* network. It uses a `nginx:latest` image and mounts as volumes the configuration file and the HTTPS certificates.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contact & Collaborate

Contact with me to collaborate :)

- gera1397@gmail.com
- GitHub: [MegaGera](https://github.com/MegaGera)