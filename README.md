# Tryton Docker-Compose

Docker Compose file to install [Tryton ERP](https://hub.docker.com/r/tryton/tryton) with two commands

Created from the offical Docker guide [here](https://discuss.tryton.org/t/how-to-run-tryton-using-docker/3200)

Due to limitations of Docker Compose the initialization of the Postgres database is run after the tryton Container is already started. This does not cause Issues so far.

---

## How to run
1. Clone the repository and go to folder
   ```bash
   git clone
   cd  
   ```
2. Export the Postgres password as env variable:
   ```bash
   export POSTGRES_PASSWORD='your_top_secret_password'
   ```

3. Run docker-compose up
   ```bash
   docker-compose --project-name tryton up -d
   ```

4. Initialize database   
   ```
   docker-compose --project-name tryton run tryton trytond-admin -d tryton --all
   ```

5. Restart tryton service

   ```
   docker-compose --project-name tryton restart tryton
   ```

6. Finished
   Tryton should now be reachable under `your-IP:8000`

* (Other trytond-admin commands)
   All trytond-admin commands should be run the same way as the first
   ```bash
   docker-compose --project-name tryton run tryton trytond-admin