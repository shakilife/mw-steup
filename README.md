# mw-setup
# wikimedia
MediaWiki helps you collect and organize knowledge and make it available to people. It's powerful, multilingual, free and open, extensible, customizable, reliable, and free of charge.

# Setup
### Note: setup reference link https://www.mediawiki.org/wiki/Manual:Running_MediaWiki_on_Red_Hat_Linux

1. Build a docker image and push to docker repository.
 ```bash
 docker build “dockerepo/reponame:latest” .
 ```
2. Edit and add credentials to sect.yaml and apply on the kubernetes cluster.
 ```bash
 kubectl apply -f sect.yaml
   ```
3. Apply deployment manifest to run mediawiki pod.
 ```bash
 kubectl apply -f mediawiki.yaml
  ```
4. You can expose service to Loadbalancer or use it internally.
5. Run URL you will get a wikimedia installation page. Follow Generate LocalSetting.php to complete the setup.

# Jenkins pipeline:
1. You can create jenkins pipeline to setup wikimedia on kubernetes cluster.
2. Jenkins pipeline will deploy helm chart to create service and deployment for wikimedia.


# Generate LocalSetting.php
1. Use your web browser to go to the MediaWiki installation URL.
2. At the LocalSettings.php not found page, click set up the wiki.
3. Select the language you want, and then click Continue.
4. MediaWiki checks the installation environment:
5. On the Connect to database page, under Database type, click MySQL.
6. Confirm that the Database host text box is set to localhost or 127.0.0.1.
7. In the Database name text box, type the name of the database you created in step 6.
8. If you want to use a database table prefix, type it in the Database table prefix text box.
9. In the Database username text box, type the name of the database user you created in step 6.
10. In the Database password text box, type the password for the database user you created in step 6.
Click Continue.
11. If MediaWiki cannot connect to the database, you receive a DB connection error message. Check the values you specified in steps 7, and then try again.
12. On the Database settings page, select the settings you want, and then click Continue.
13. On the Name page, type a name for your wiki.
14. Under Administrator account, fill in the text boxes to create an account.
15. Click Ask me more questions, and then click Continue.
16. On the Options page, select the settings you want, as well as any extensions you want to install, and then click Continue.
17. On the Install page, click Continue.
18. When the installation process finishes, click Continue. The Complete! page appears.
19. Save the LocalSettings.php file on your local computer.
20. upload the LocalSettings.php file to the directory where you installed MediaWiki.
21. On the Complete! page, click enter your wiki. The wiki's main page appears.
22. Click Log in to log in to the wiki, and then use the username and password.

