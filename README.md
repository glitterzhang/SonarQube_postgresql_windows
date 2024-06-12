# Setup SonarQube, postgresql and Sonar Scanner on windows for statistic analysis

### 1. Documents:
https://docs.sonarsource.com/sonarqube/latest/

### 2. Three components:
- Analyzer | A client application that analyzes the source code to compute snapshots.
- Database	| Stores configuration and snapshots.
- Server |	Web interface that is used to browse snapshot data and make configuration changes.

![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/0c235ec0-5113-4078-b97e-2c51155a467d)

### 3. Prerequisites:
  1. A 64-bit system.
  2. A Java runtime environment: 
Oracle JRE or OpenJDK.
Minimum version: Java 17.  https://www.oracle.com/java/technologies/downloads/#jdk17-windows

### 4. Download SonarQube and Sonar Scanner
+ SonarQube :https://www.sonarsource.com/products/sonarqube/downloads/
+ Sonar Scanner:https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/scanners/sonarscanner/
![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/0ee7d0a2-362a-4287-9ac5-f00391e58802)

### 5. Download postgreSQL
https://www.postgresql.org/download/windows/

### 6. Connect SonarQube with PostgreSQL
  + create database in PostgreSQL:sonar 
  + create a user in PostgreSQL:sonar pw: 1234
 in directory "~\sonarqube-10.5.1.90531\conf"
set

```
sonar.jdbc.url=jdbc:postgresql://localhost/sonar?currentSchema=public
sonar.jdbc.username=sonar
sonar.jdbc.password=1234
```
### 7. Load SonarQube
   - click **StartSonar.bat** under "C:\Users\xx\sonarqube-10.5.1.90531\bin\windows-x86-64\"
     ![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/35e996c2-e20d-4ed2-80cc-2ad69d31d89e)

   - open web with http://localhost:9000

### 8. Create Project
1. creat project key
![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/79d73cda-d2fb-4ff0-898b-29eacb52448d)

2. Use `global setting`

3. Set up the way of analysis- we use `locally`
    ![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/8724d6f3-9382-4288-bb6e-389eaab6a1cd)

4. Generate the token
   ![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/ae6f58a5-4390-4759-8054-e81d3f8ac40b)
   ![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/0b50fdfc-65e1-4e94-adf2-86edfd03d5c0)
5. Run analysis, our system is windows and all code are developed with python.
![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/814452bc-f265-4e3f-99ce-97327f8d629f)

 6. Before you run the analysis,set the proporties in sonar.properies in directory "~\sonarqube-10.5.1.90531\conf"

```
  sonar.login=admin
  sonar.password=adminpassword
  sonar.projectKey=test
  sonar.projectName=test
  sonar.projectVersion=1.0
  sonar.sources=~\projectdirectory
  sonar.projectBaseDir=\projectdirectory
  sonar.sourceEncoding=UTF-8
```
8. Execute the above commands in step 5 "sonar-scann.bat ...." in your project's folder .
9. If succeed, the result will be displayed on the dashbord.

