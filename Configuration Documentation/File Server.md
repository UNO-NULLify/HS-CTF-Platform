# File Server Configuration Documentation

The fileserver is run in a docker container, which can be configured by performing the following steps. [A sample Dockerfile can be found here]() and can be adapted easily following these instructions or those in the sample Dockerfile.

1. Create a file called ```Dockerfile```.

2. Open the file in a text editor

3. Set the container image by typing ```FROM debian:stretch-slim``` on the first line.

4. On a new line, tell it to install the required packages by typing ```RUN apt-get update && apt-get install -y apache2```.

5. One a new line, make a directory for a category by typing ```RUN mkdir -p /var/www/html/CategoryNameHere``` and replace CategoryNameHere with the category name.

6. Perform step 5 for all category names.

7. 