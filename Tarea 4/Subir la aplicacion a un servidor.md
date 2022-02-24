Subir la aplicacion a un servidor



- Instalamos mysql server y mysql client

  ```bash
  apt-get install mysql-server mysql-client
  ```

  <img src="C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222202045929.png" alt="image-20220222202045929" style="zoom:200%;" />

- Creamos la instalacion segura de mysql

```bash
mysql_secure_instalation
```

![image-20220222202420229](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222202420229.png)

![image-20220222202500988](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222202500988.png)

- Entramos como root

```bash
mysql -u root -p
```

![image-20220222202627285](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222202627285.png)

- Vemos las bases de datos creadas en el sistema y creamos la BBDD test_virtual

```bash
show databases;
create database test_virtual;
```

![image-20220222202815935](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222202815935.png)

- Creamos el usuario 'user'

```bash
create user 'user'@'localhost' identified by 'user';
```

![image-20220222202924327](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222202924327.png)

![image-20220222203005338](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222203005338.png)

- Damos privilegios al usuario sobre esta tabla

```bash
grant all privileges on test_virtual.* to 'user'@'localhost' with grant option;
```

![image-20220222203453785](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222203453785.png)

- Nos logueamos como usuario para ver la base de datos.

```bash
mysql -u user -p
```

![image-20220222203655205](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222203655205.png)

- Instalamos Java, hay que instalar maven previamente.

```bash
apt-get install maven
```

![image-20220222203901689](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222203901689.png)

- Instalamos jpk8

```bash
apt-get install openjdk-8-jdk
```

![image-20220222204055546](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222204055546.png)

- Comprobamos la versión de Java actual.

```bash
java -version
```

![image-20220222204200170](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222204200170.png)

- Instalamos el servidor ftp

```bash
apt-get install vsftpd
```

![image-20220222204310250](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222204310250.png)

- Editamos el archivo de configuración vsftpd y habilitamos la escritura del local user

```bash
nano /etc/vsftpd.conf
```

![image-20220222204614419](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222204614419.png)

- Reiniciamos el servicio sftpd.

```bash
systemctl restart vsftpd.service
```

![image-20220222204751169](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222204751169.png)

- Comprobamos que esté habilitado.

```bash
systemctl is-enabled vsftpd.service
```

![image-20220222204921199](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222204921199.png)

- Arrancamos Filezilla y nos conectamos con nuestra ip.

![image-20220222205039273](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222205039273.png)

- Subimos nuestro trabajo a nuestra carpeta /home/master

![image-20220222205221434](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222205221434.png)

![image-20220222205248869](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222205248869.png)

- Accedemos a la ruta donde hemos subido nuestro trabajo.

![image-20220222205424833](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222205424833.png)

- Editamos el fichero pom.xml

![image-20220222205530669](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222205530669.png)

- Instalamos maven

```bash
mvn install
```

![image-20220222205737983](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222205737983.png)

- Ejecutamos para ver si funciona

```bash
 java -jar target/virtual-jar
```

![image-20220222205858764](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222205858764.png)

- Desde el navegador, accedemos con nuestra IP y el puerto 8080 para ver que todo funciona correctamente

![image-20220222210008838](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222210008838.png)

- Creamos un servicio para que, cuando el servidor arranque, arranque el servicio de Srping.

 Le añadimos las siguientes instrucciones:

![image-20220222210254246](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222210254246.png)

- Comprobamos que el servicio de Spring esté habilitado.

```bash
systemctl is-enabled spring.service
```

![image-20220222210415243](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220222210415243.png)

