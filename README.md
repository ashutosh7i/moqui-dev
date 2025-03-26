## Moqui Runtime

The default runtime directory for Moqui Framework. A runtime directory is required for Moqui Framework to run, it contains components, utilities and configurations.

### Included Utility Components

This project comes with the following pre-installed components:
- **mantle-udm**: Universal Data Model for Moqui.
- **mantle-usl**: Universal Service Library for Moqui.
- **simpleScreens**: A set of simple and reusable screens for common use cases.


### Setting Up the Database

To set up the database, follow these steps:

1. Log in to your MySQL server:
    ```bash
    mysql -u root -p
    ```

2. Create the database:
    ```sql
    CREATE DATABASE moqui;
    ```

### Add an appropriate mysql connector

Moqui framework requires a mysql connector to use database, it is a standard process in java ecosystem, to use mysql or any database download suitable connector according to your database version or use the latest one.

There are two ways to adding a connector-

1. Download appropriate connector and place it in the `framework/runtime/component/lib` directory.
2. TODO- adding a connector via gradle script.


### Database Configuration

This project includes pre-configured settings for MySQL. The database configuration can be found in `conf/MoquiDevConf.xml`:

```xml
<datasource group-name="transactional" database-conf-name="mysql" schema-name="">
    <inline-jdbc jdbc-uri="jdbc:mysql://127.0.0.1:3306/moqui
    ?autoReconnect=true&amp;useUnicode=true&amp;characterEncoding=UTF-8"
    jdbc-username="dbuser"
    jdbc-password="password"
    pool-minsize="2"
    pool-maxsize="50"/>
</datasource>
```

Ensure that the MySQL database is set up and accessible with the above credentials and configurations are properly created before proceeding with the application setup.

### Steps to Set Up and Run

1. Run the following command to get the runtime:
    ```bash
    ./gradlew getRuntime
    ```

2. Load the necessary data:
    ```bash
    ./gradlew load
    ```

3. Start the application:
    ```bash
    ./gradlew run
    ```
