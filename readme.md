## Spring boot - Simple CRUD API With MariaDB & Swagger

## System Requirements
- Java openjdk : ( version "11.0.18")
- Spring Boot : (version 2.7.11)
- MariaDB : (Version 10.4.28)
- Maven : (Apache Maven 3.9.1)
- Editor : (Intellij IDEA 2023.1.1 Community Edition)


## run project

1. clone project Spring boot - Simple CURD API With Swagger
```
git clone https://github.com/rardan97/spring-boot-curd-mariadb-swagger.git
```

2. add new database mysql with name "db_curd_api"

3. open project with intellij IDEA then edit config database in application.properties change database name, username and password match your config db

   #### location : spring-boot-curd-mariadb-swagger/src/main/resources/application.properties

```
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://localhost:3306/your_database
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
#spring.jpa.show-sql: true
```


4. open terminal input command 
```
mvn clean install 
```
5. if success next input command 
```
mvn spring-boot:run
```

6. open your browser input url 
``` 
http://localhost:8080/swagger-ui/index.html#/ 
```
![img.png](img.png)

## Add Data Product
This is API endpoint as a create new data product

### Request URL
```
- POST http://localhost:8080/api/v1/produk/add
```

### Request body
```json
{
    "produkName": "ayam goreng",
    "produkHarga": 1000,
    "produkKategori": "makanan",
    "produkStok": 5
}
```

### Response
```json
{
  "status": true,
  "statusCode": "OK",
  "message": [
    "Berhasil Menambahkan Data Product"
  ],
  "data": {
    "id": 3,
    "produkName": "ayam goreng",
    "produkHarga": 1000,
    "produkKategori": "makanan",
    "produkStok": 5
  }
}
```


## Get List Data Product
This is API endpoint as a get List all data product

### Request URL
```
- GET http://localhost:8080/api/v1/produk/index
```

### Request
```
No parameters
```

### Response
```json
{
    "status": true,
    "statusCode": "OK",
    "message": [
      "Data ditemukan, menampilkan data dari database"
    ],
    "data": [
        {
            "id": 1,
            "produkName": "ayam goreng",
            "produkHarga": 1000,
            "produkKategori": "makanan",
            "produkStok": 5
        }
    ]
}
```

## Update Data Product
This is API endpoint as a update data product existing by id

### Request URL
```
- PUT http://localhost:8080/api/v1/produk/update/1
```

### Request body
```json
{
  "produkName": "Ayam Bakar",
  "produkHarga": 20000,
  "produkKategori": "makanan",
  "produkStok": 50
}
```

### Response
```json
{
  "status": true,
  "statusCode": "OK",
  "message": [
    "Update Produk Dengan ID : 1| Berhasil di update."
  ],
  "data": {
    "id": 1,
    "produkName": "Ayam Bakar",
    "produkHarga": 20000,
    "produkKategori": "makanan",
    "produkStok": 50
  }
}
```


## Delete Data Product
This is API endpoint as a delete data product by id
### Request URL
```
- DELETE http://localhost:8080/api/v1/produk/delete/1
```

### Request
```
No parameters
```

### Response
```json
{
    "status": true,
    "statusCode": "OK",
    "message": [
      "Produk dengan ID : 2, berhasil di hapus"
    ],
    "data": null
}
```

