# Ansible Playbook – SSL Certificates with Lego (Let's Encrypt)

This Ansible playbook automates the installation and configuration of [Lego](https://go-acme.github.io/lego/), a Let's Encrypt client written in Go, to obtain SSL/TLS certificates using DNS-01 challenges.  
It currently supports the following DNS providers:

- **Cloudflare**
- **ArvanCloud**

---

## 🚀 Features

- Installs [Lego](https://go-acme.github.io/lego/) on the target host.
- Automates the DNS-01 ACME challenge.
- Requests and renews SSL/TLS certificates from Let's Encrypt.

---

## 🌐 Cloudflare API 

1. Log in to your Cloudflare account.  
2. Click on **"Manage Account"** and then choose **"Account API Tokens"**.  
3. Click on **"Create Token"**.  
4. Use the **"Edit zone DNS"** template.  
5. Add permissions: **Zone:Edit** and **Zone:Read**.  
6. Save the API token securely.  

---

## 🌐 ArvanCloud API

Follow [ArvanCloud documentation](https://docs.arvancloud.ir/fa/accounts/iam/machine-user) to:  
1. Create a machine user with an API key.  
2. Create an access policy with the **DNS Management** permission.  

---

## 🔑 Obtaining the First SSL Certificate

1. Add your first host (example below) in:  

```bash
inventory/hosts.ini
```  

2. Create a config file by copying:  

```bash
host_vars/example.yml
```  

3. Edit the new file with your own data.  

4. Run the playbook:  

```bash
ansible-playbook -i ./inventory/hosts.ini lego.yml -vvv
```

📂 The new certificates will be stored in:  

```bash
~/.lego/certificates/
```

---

## 🙌 Contributions

Pull requests and issues are welcome!  
