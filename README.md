# **RETROWAVE** #

## OVERALL PRESENTATION ##

### What is RETROWAVE? ###
**RETROWAVE** is an E-commerce site developped by a team of [sudents developpers](https://github.com/EpitechIT2020/W-WEB-502-PAR-2-2-ecommerce-hugo.kerivel-larriviere/blob/master/README.md#authors) as a project for Web@cademie by EPITECH. It is aimed to emulate an real E-commerce site that sell 80's themed objects such as arcade terminals, printed shirts with retro designed, etc.

### organization ###
The site is divised in two subproject and a database:
1. A **React interface** (more details [here](https://github.com/EpitechIT2020/W-WEB-502-PAR-2-2-ecommerce-hugo.kerivel-larriviere/blob/master/README.md#react-inteface)) :
The user interface is developped in Javascript using the React library. Users can register, login and buy items from this interface. 
2. A **Symfony API** (more details [here](https://github.com/EpitechIT2020/W-WEB-502-PAR-2-2-ecommerce-hugo.kerivel-larriviere/blob/master/README.md#symfony-api)) :
The symfony API use the requests from the react interface and return results from the database.
3. a **MySQL database** (more details [here](https://github.com/EpitechIT2020/W-WEB-502-PAR-2-2-ecommerce-hugo.kerivel-larriviere/blob/master/README.md#mysql-database)) :
 The DB register data from users, products, and orders.
 
 ### More ###
 
## STARTING THE PROJECT LOCALLY ##
### Requirements ###
● [Composer](https://getcomposer.org/download/)

● [Node.js and npm](https://nodejs.org/en/download/)
### Symfony side ###
1. cd into subdirectory "e-commerce-symfony"
2. execute :
```bash
composer update
composer install
```
then 
```bash
symfony server:start
```
### React side ###
1. cd into subdirectory "e-commerce-react"
2. execute: 
```bash
npm update
npm install
```
then
```bash
npm run start
``` 
3. wait for the browser to pop-up and load the page

## TECHNICAL PRESENTATION ##
 
 ### React Inteface ###
 1. **All product display page** (/products):
 this page display the full list of items sold by the site. The interface fetch on a API url that return all the items registered in the database in JSON. Clicking on an item give access to this item detailed presentation of it
 2. **specific item presentation** (/products/:id):
 This page fully details the item. It display the title of the item, its price, category, color, size, available stock, and a description. A short form let the users add the item to their cart with a specified quantity.
 3. **Profile display and edit page** (/profile):
  This page give the users access to their profile edit form. It display all their information as an editable form.
 4. **Register form** (/register):
  User can register here. They have to fill the form with their first name, last name, birthdate, an email adress and a password. These two last informations will be used to log in. Once register form complete and sent, users will recieve an email to complete registration.  
 5. **login form** (/login):
  users can use their email adress and password previously used during registration to login and access their cart and profile, and order items.
 6. display Cart(/panier):
  display all the items users added to their carts. Show command with "panier" state from the user account. 

### Symfony API ###
1. **All products** (/product):
 return all products from the database in JSON
2. **One product** (/product/:id):
 return every informations of the item associated with the id from the database in jSON
3. **Edit product** (/product/:id/edit):
 route to edit a specific product in the DB only accessible to administrators.
4. **all Users** (/users):
 return all users informations from the database in JSON.
5. **One User** (/users/:id):
 return all informations of the user associated to the id from the database in JSON.
6. **Edit User** (/users/:id/edit):
 route to edit user informations in the DB from the user interface.
7. **add User** (/users/new):
 route to add a user into the DB. Show a form to add user only accessible to administrators.
 
### MySQL database ###
The "e-commerce" database is organized in seven tables:
1. **carte_bancaire**: 
 register credit cards number (num_cb), expiration date(date_exp) and user first and last name (nom_prenom). Linked to "Users" with "user_id" key.
2. **commande**:
 register price (montant), date (date_enregistrement) and "panier" state (etat) of each order. Linked to "Users" with "user_id" key.
3. **commentaire**:
 register text (commentaire) and date (date) of each comment on every items. Linked to "Products" with "id_produit" key and to "Users" with "user_id" key.
4. **detail_commande**:
 register quantity (quantité) and price (prix) of each item of each order. Linked to "Products" with "id_produit" key and to "Commande" with "commande_id" key.
5. **Doctrine_migration_version**:
 register all version of migrations.
6. **product**:
 register the reference (reference), category (category), name (title), description (description) color (color), size (size), picture (photo), price (price) and avalaible stock (stock) of each product.
7. **users**:
 register hashed password (mdp), first (name) and last name (lastname), email adress (email), city fo residence (city), postal code (postal_code), precise adress (adress), admin status (statut), roles (roles), and verified status (is_verified) of each user registered.
 
## AUTHORS
● [**Hugo Kerivel Larrivière**](https://github.com/Ukher) - developper

● [**Floran Lebreton**](https://github.com/Floran123) - developper

● [**Thibaut Jager**](https://github.com/ThibautWa) - developper

● [**Nicolas-Andrei Corlan**](https://github.com/Vulcanosaurus) - developper

● [**François Verin**](https://github.com/FVERIN-EPITECH) - graphist
