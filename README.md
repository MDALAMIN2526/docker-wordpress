1. **Update a `.env` File**

   In your `wordpress-docker` directory, update the `.env` file with the following content:

   ```env
   MYSQL_DATABASE=wordpress
   MYSQL_USER=wordpress
   MYSQL_PASSWORD=wordpress
   MYSQL_ROOT_PASSWORD=somewordpress
   PORT=8000
   ```


2. **Create the Volumes and Start the Docker Containers**

   Run the following command, specifying the name of your Compose file:

   ```sh
   docker-compose -f wordpress.yml up -d
   ```

   This command will create the `wordpress_data` and `db_data` volumes if they do not already exist and start the WordPress and MySQL containers.

3. **Verify the Volumes**

   You can verify that the volumes have been created and are being used by running:

   ```sh
   docker volume ls
   ```

   You should see `wordpress_wordpress_data` and `wordpress_db_data` in the list of volumes.

4. **Access Your WordPress Site**

   Open your web browser and navigate to `http://localhost:8000` (or the port number you specified in the `.env` file). Complete the WordPress setup using the provided database details.

By specifying the `-f` flag followed by the file name, Docker Compose knows which file to use for the configuration, allowing you to have multiple Docker Compose files in your project with different configurations.
