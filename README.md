# 📦 Ansible Mini Webserver

Tento repozitář obsahuje jednoduchý Ansible playbook, který na vzdáleném serveru nainstaluje Apache webserver, nahraje vlastní `index.html` a spustí službu.

---

## 📁 Struktura projektu

ansible-mini-webserver/ <br>
├── inventory <br>
├── playbook.yml <br>
├── roles/ <br>
│ └── webserver/ <br>
│ ├── tasks/ <br>
│ │ └── main.yml <br>
│ ├── files/ <br>
│ │ └── index.html <br>
│ └── handlers/ <br>
│ └── main.yml <br>




---

## ⚙️ Co to dělá

- Nainstaluje Apache (`apache2`)  
- Zkopíruje vlastní `index.html` do `/var/www/html/`  
- Spustí a povolí službu Apache  
- (Volitelně) otevře port 80

---

## 🚀 Jak to spustit

1️⃣ **Nastav inventář**

Otevři soubor `inventory` a nastav IP adresu a přístupové údaje:

```ini
[web]
192.168.1.100 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
```

##  Soustime
ansible-playbook -i inventory playbook.yml


 ## Po nasazení

    Otevři prohlížeč a zadej IP serveru.

    Měl by se zobrazit vlastní index.html s hláškou „It works!“.

## Požadavky

    Linux server (např. Ubuntu) s SSH přístupem

    Ansible nainstalovaný na tvém počítači

## Odinstalace
```bash
sudo apt remove apache2
```

## Happy automation! 🤖✨
