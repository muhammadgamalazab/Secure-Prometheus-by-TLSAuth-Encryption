# Securing Prometheus with Authentication and Encryption

This project demonstrates how to secure Prometheus by implementing authentication and encryption, inspired by the article [Authentication & Encryption in Prometheus](https://itsmegaffoor.medium.com/authentication-encryption-in-prometheus-d13e6e6299ad).

## Table of Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Generate SSL Certificates](#generate-ssl-certificates)
4. [Configure Prometheus](#configure-prometheus)
5. [Set Up Basic Authentication](#set-up-basic-authentication)
6. [Test the Setup](#test-the-setup)

## Introduction
Prometheus is a powerful monitoring tool used to collect and query metrics. By default, Prometheus does not provide authentication, which can be a security risk. This guide will walk you through securing Prometheus by enabling HTTPS and basic authentication.

## Requirements
- Prometheus installed and running
- OpenSSL installed for generating certificates
- An HTTP reverse proxy such as Nginx or Apache (optional, for managing authentication)

## Generate SSL Certificates
Use OpenSSL to generate a self-signed SSL certificate.

```bash
openssl req -newkey rsa:2048 -nodes -keyout prometheus.key -x509 -days 365 -out prometheus.crt
