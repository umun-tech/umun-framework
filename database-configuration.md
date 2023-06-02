# Database Configuration

### Automatically create and update tables according to your entities in the DB

```
spring.jpa.hibernate.ddl-auto=update
```

## MySQL
To create highly scalable server backends, you may choose to use MySQL as your database. To use that add the following to your application's `application.properties`.

```
spring.datasource.url= jdbc:mysql://localhost:3306/<YOUR-DATABASE-NAME>?useUnicode=yes&characterEncoding=UTF-8
spring.datasource.username=<YOUR-MYSQL-USERNAME>
spring.datasource.password=<YOUR-MYSQL-PASSWORD>
```


## H2
You may choose to use the embedded H2 database, if you are deploying on a offline machine for individual users.


Add the following dependency in your `pom.xml`

```
  <dependency>
      <groupId>com.h2database</groupId>
      <artifactId>h2</artifactId>
      <scope>runtime</scope>
  </dependency>
```

Add the following configuration in your `application.properties`

```
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=any_user_name_here
spring.datasource.password=any_password_here
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
#The web-allow-others setting allows connections from a web browser running on a different machine.
spring.h2.console.settings.web-allow-others=true
```

> You may use any password or username for h2. You need to use the same when you try to access through h2-console.

### Keep database in memory
```
#spring.datasource.url=jdbc:h2:mem:testdb
```

### Keep database in a file
```
spring.datasource.url=jdbc:h2:file:<Exact_file_path>
```

### Keep database in resources folder itself
```
spring.datasource.url=jdbc:h2:file:./src/main/resources/data
```


