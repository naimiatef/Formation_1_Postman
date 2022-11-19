L'objectif de cette formation est de :
   #### Postman Core :
- Simple Postman request
- Build our API server
- GET Request
- Post Request
- Put Request
- Delete Request
- ostman Collections
- Postman Test cases
- What is JSON
- Json path using postman
- Postman Environment variables
- Get and Set Environment variables using code
- Global Variables
- Postman Mock
   #### Postman Authorization :
- Download and configure Json server auth
- Secure our API
- Use postman Authorization
   #### Newman:
- Build our E2E testing
- Run the E2E testing manually using Postman
- Download and configure Newman
- Run the E2E test using Newman
- Build HTML report for Newman results
   #### Jenkins :
- Download and configure Jenkins
- Create new Jenkins job to run our E2E Testing
- Run Jenkins job automatically periodically

# Plans:
# 1. # Création d'une Api avec **json Server**.
     A- installation de Node.js:  https://nodejs.org/en/download/
     B- Vérification de l'installation de Node.js avec la commande : **node-v**
     C- Installation de Visual Studio Code : https://code.visualstudio.com/download
     D- Installation de Json server avec la commande : **npm install -g json-server**
     E- Création d'une API **db.json**
     F- Démarrer le serveur JSON :  **json-server --watch db.json**
     G-
 ![image](https://user-images.githubusercontent.com/7100940/202845870-f355c14a-2e1e-4347-abb5-ef36ccc5b3db.png)

# 2. # Création d'une requête Get :
![image](https://user-images.githubusercontent.com/7100940/202846453-95f0a769-b5da-47f2-8619-e382e92a6224.png)
     
     **- les parametres avec Get:**
     
 http://localhost:3000/courses?title=Javascript
![image](https://user-images.githubusercontent.com/7100940/202848706-f55233d9-6509-4577-92d5-1b194fb7d484.png)
# 3. # Création d'une requête Post :
![image](https://user-images.githubusercontent.com/7100940/202848894-c0083aba-5a7c-4236-880f-57fb4252d75b.png)

# 4. #  Création d'une requête Put :
![image](https://user-images.githubusercontent.com/7100940/202849046-22ba398c-ac4f-4ce6-aab5-c9851e4130a5.png)

# 5. #  Création d'une requête Delete :
![image](https://user-images.githubusercontent.com/7100940/202849302-d26ae665-d5f4-4559-a29e-084c05c3a687.png)

# 6. # Postman Set Environment Variable :
![image](https://user-images.githubusercontent.com/7100940/202850213-97ddd8f8-6e1c-4388-ade0-e19037fc9064.png)

# 7. # Postman environment Variables and Tests:
![image](https://user-images.githubusercontent.com/7100940/202850153-0fba3ce8-f4e1-49b3-a043-9ac7d8df00e5.png)
```
var jsonFile=pm.response.json() 
var courseID= jsonFile.id

//enregistrer l'id qui se trouve dans la variable courseID dans une variable d'environnement  appelée  cours
pm.environment.set("cours",courseID);

pm.test("Response time is less than 201ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(201);
});
```
# 8. # Postman Mock API:
***Mock server:*** est un serveur qui n’est pas un serveur réel. C’est juste un faux serveur qui est simulé pour fonctionner comme un vrai serveur afin que nous puissions tester nos API et vérifier la réponse ou les erreurs.
# 9. # Postman Install Json Server Auth :
pour installer **Json Server Auth** tapez la commande: 
```npm install -D json-server-auth```

![image](https://user-images.githubusercontent.com/7100940/202866761-f7993f2f-21ef-49d1-b95a-2f1b8254742d.png)

# 9. # lancer le serveur :
``` json-server db.json -m ./node_modules/json-server-auth ```
![image](https://user-images.githubusercontent.com/7100940/202866972-fa745ac6-c9d4-4d12-8e6f-f4073e786bd9.png)


# 10. # Création d'un "accessToken": 

![image](https://user-images.githubusercontent.com/7100940/202867108-e5f345c1-dd79-466f-b7e7-f27a6e51a000.png)

# 11. # Guarded routes: 

![image](https://user-images.githubusercontent.com/7100940/202867235-dc574ede-5c36-4067-8992-ef17c4217ced.png)

voir : https://www.npmjs.com/package/json-server-auth

# 12. # Authorization : 

![image](https://user-images.githubusercontent.com/7100940/202868597-885f6898-0b86-47f1-8b52-06214fac614f.png)

# 13. # exécution de collection par newman :
- Newman est un outil CLI (Command-line interface) qui vous permet d’exécuter une collection Postman directement à partir de la ligne de commande. 
- A- exporter la coolection avec l'extension ***nom_collection.json***
- B- exporter les variables d'environnement avec l'extension ***nom_variable_evt.json***

![image](https://user-images.githubusercontent.com/7100940/202869262-217c89f8-98c9-4010-a7df-ee63fef7b612.png)

# 14. # Construire un rapport HTML par newman :

- A- installation de newman-reporter-htmlextra 
``` npm install -g newman-reporter-htmlextra 
- voir : https://www.npmjs.com/package/newman-reporter-htmlextra

- B- exécuter la commande ``` newman run collection.json -e variableevt.json -r htmlextra ``` pour générer un rapport HTML

![image](https://user-images.githubusercontent.com/7100940/202869679-c8e97b0b-3a40-45c1-9b0e-3b3f3dd1d0cb.png)
