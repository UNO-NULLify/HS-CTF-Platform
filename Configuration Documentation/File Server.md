# File Server Configuration Documentation

The fileserver is run in a docker container, which can be configured by performing the following steps. [A sample Dockerfile can be found here]() and can be adapted easily following these instructions or those in the sample Dockerfile. The Dockerfile created will be managed by the central Dockerfile and the container will start by running ```Docker up``` in the root directory.

1. Create a file called Dockerfile: ```touch Dockerfile```.

2. Open the file in a text editor

3. Set the container image by typing ```FROM debian:stretch-slim``` on the first line.

4. On a new line, tell it to install the required packages by typing ```RUN apt-get update && apt-get install -y apache2```.

5. On a new line, make a directory for a category by typing ```RUN mkdir -p /var/www/html/CategoryNameHere``` and replace CategoryNameHere with the category name.

6. Perform step 5 for all category names.

7. On a new line, paste the follwing to copy the index.html, replacing Static_Files with the path to the index.html:
```RUN rm /var/www/html/index.html```
```COPY Static_Files/index.html /var/www/html/```

8. Make a directory for each challenge, changing the CategortyNameHere to the category name and 100 to the challenge point value:
```RUN mkdir -p /var/www/html/CategoryNameHere/CategoryNameHere100```


9. Copy the challenges to the correct location, replacing PathToChallengeFile with the path to the file that needs to be served, CategoryNameHere with the category, and 100 with the point value of the challenge:
```COPY PathToChallengeFile /var/www/html/CategoryNameHere/CategoryNameHere100```

10. Repeat steps 8 and 9 for all challenges

11. Change ownership of the index file: ```RUN chown -R www-data:www-data /var/www/html/*```