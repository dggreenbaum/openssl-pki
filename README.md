OpenSSL PKI
=========
[![Ansible Galaxy](https://img.shields.io/badge/role-dggreenbaum.openssl--pki-blue.svg)](https://galaxy.ansible.com/dggreenbaum/openssl-pki/) [![Build Status](https://travis-ci.org/dggreenbaum/openssl-pki.svg?branch=master)](https://travis-ci.org/dggreenbaum/openssl-pki)

This role sets up a root certificate authority (CA), an arbitrary number of intermediate CAs (EG for each environment), and an arbitrary number SSL/TLS keys and certificates signed by those  CAs.

Requirements
------------

Requires a Unix like operating system. (Linux/OSX) The latest Debian/Ubuntu are supported.

This role will attempt to install the openssl package or equivilant for your operating system. If your operating system does not have an openssl package (EG Windows)m this role won't work.

Role Variables
--------------

|CA Location|Default|
|---|---|
|openssl_pki_certs_ca_root_dir|"{{ ansible_env.HOME }}/ca"|
|openssl_pki_certs_server_root_dir|"{{ ansible_env.HOME }}/srv"|

|CA Names|Default|
|---|---|
|openssl_pki_ca_name|"ca"|
|openssl_pki_intermediate_ca_name|"intermediate"|

|Cert Fields|Default|
|---|---|
|openssl_pki_country|"US"|
|openssl_pki_locality|"Phoenix"|
|openssl_pki_organization|"Example\\ LLC"|
|openssl_pki_state|"Arizona"|

|CA Common Names|Default|
|---|---|
|openssl_pki_ca_common_name|"Example\\ LLC\\ Certificate\\ Authority"|
|openssl_pki_intermediate_common_name|"Example\\ LLC\\ Intermediate\\ Certificate\\ Authority"|

|Server Common Name|Default|
|---|---|
|openssl_pki_server_common_name|"{{ inventory_hostname }}"|

|Server Alternative Names|Default|
|---|---|
|openssl_pki_server_alternative_names|["example.com"]|

|Cert lifespan|Default|
|---|---|
|openssl_pki_server_cert_days|"365"|
|openssl_pki_intermediate_cert_days|"3650"|
|openssl_pki_ca_days|"7300"|

|Hashing method|Default|
|---|---|
|openssl_pki_hash_type|"sha256"|

|File modes|Default|
|---|---|
|openssl_pki_private_dir_mode|"0700"|
|openssl_pki_ca_key_mode|"0400"|
|openssl_pki_ca_cert_mode|"0444"|
|openssl_pki_intermediate_key_mode|"0400"|
|openssl_pki_intermediate_cert_mode|"0444"|
|openssl_pki_intermediate_chain_mode|"0444"|
|openssl_pki_server_key_mode|"0400"|
|openssl_pki_server_cert_mode|"0444"|

|Key Strength|Default|
|---|---|
|opsnssl_pki_ca_key_strength|"4096"|
|opsnssl_pki_intermediate_key_strength|"4096"|
|opsnssl_pki_server_key_strength|"2048"|

Dependencies
------------

This role should not have any role dependencies.

Example Playbook
----------------

banana banana banana

License
-------

BSD
