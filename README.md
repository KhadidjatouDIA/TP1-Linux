# 🚀 Projet Nginx & MySQL avec Vagrant
## Description
Ce projet utilise Vagrant pour configurer un environnement de développement avec :
- Un serveur web Nginx
- Un serveur MySQL
- Une mini application front
## Prérequis
- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

### 1. Initialisation et configuration de Vagrant
```sh
vagrant init
```
![alt text](image.png)
![alt text](image-3.png)
### 📝 Cela génère un fichier Vagrantfile de configuration.

## ⚙ Configuration du Vagrantfile
#### Modifiez le fichier Vagrantfile pour définir la machine virtuelle souhaitée sur VSCode ou votre éditeur préféré. <br>
#### Choisissez une box : Visitez Vagrant Cloud et sélectionnez bento/ubuntu-22.04.
![alt text](image-1.png)

## ✅Validation et Démarrage de la VM
<h3> Après avoir configuré le Vagrantfile, vous pouvez valider la configuration avec cette commande pour vérifier si la configuration est correcte. </h3> 

### 1️⃣ Validez votre configuration
#### Cette commande permet de vérifier si la configuration est correcte :
```sh
vagrant validate
```
![alt text](image-2.png)

### 2️⃣ Démarrez la machine virtuelle
```sh
vagrant up
```
#### 💡 Cela lance la VM.
![alt text](image-7.png)
![alt text](image-8.png)
![alt text](image-9.png)

### 3️⃣ Accédez à la VM via SSH
```sh
vagrant ssh miniapp
```
![alt text](image-10.png)


### 4. Installer les packages: 
#### Mets à jour les paquets de la VM :
```sh
sudo apt update && sudo apt upgrade -y
```
![alt text](image-11.png)
![alt text](image-12.png)
### 5. Installer NGINX
Maintenant installez Nginx sur Ubuntu:
```sh
-sudo apt install nginx -y
```
![alt text](image-13.png)
![alt text](image-14.png)

### 5. ✅ Vérification de l'installation
#### Vérifier que Nginx est installé et actif:
![alt text](image-15.png)
```sh
systemctl status nginx
```
Donc :Si Nginx est actif, tu verras un message indiquant "active (running)

### 6. Déploiement de l'application
```sh
cd /var/www/html
```
![alt text](image-16.png)
```sh
vagrant@vagrant:~$ ls /vagrant_data
index.html
vagrant@vagrant:~$
```
![alt text](image-17.png)

### Pour deplacer le fichier index.html vers /var/www/html/:
```sh
sudo mv /vagrant_data/index.html /var/www/html/
sudo chown www-data:www-data /var/www/html/index.html
sudo chmod 644 /var/www/html/index.html
```
### Pour qu'il s'affiche dans le navigateur: 
```sh
curl http://localhost
```
![alt text](image-18.png)

#### prenez l'adresse ip de votre app
📌 Adresse IP de l'application : 192.168.33.10


#### 👉 Ouvre ton navigateur et entre l’URL suivante : `http://192.168.33.10`
![alt text](image-19.png)
![alt text](image-25.png)

### 6. Installation de MySQL Server
```sh
sudo apt install mysql-server -y
```
![alt text](image-20.png)
Se connecter à MySQL :
````sh
sudo mysql -u root
````
![alt text](image-21.png)

### 7. Création d'une table MySQL
```sql
CREATE TABLE utilisateurs (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(50),
    email VARCHAR(100),
    age INT
);
```
![alt text](image-22.png)

### 8. Pour arreter la machine:
![alt text](image-26.png)
![alt text](image-27.png)


#### 🚀 Félicitations ! Tu as configuré un environnement Vagrant avec Nginx, MySQL et une mini application front-end.
#### Si tu rencontres un problème, n'hésite pas à ouvrir une issue ! 🚀
### 👤 Auteur:
#### Khadidiatou DIA
#### 📧 Email : sokhnakhadidjah@gmail.com