## Setup

Clone the repository, install the dependencies and get started right away.

```bash
$ git clone <code_url>
$ cd <app_name>
$ npm i
```

Make a copy of `.env.example` as `.env` and update your application details, database credentials and front-end details. Now, run the migrations the database.

```bash
$ npm run migrate
```

Finally, start the application.

```bash
$ npm run start:dev
```

## Using Docker

You can run your database in docker also, for this, make `.env` file as above and run following command:

```bash
$ docker compose up -d
```

To stop docker:

```bash
$ docker compose down
```
