# Setup SonarQube, postgresql and Sonar Scanner on windows for statistic analysis

1. Documents:
https://docs.sonarsource.com/sonarqube/latest/

2. Three components:
Analyzer | A client application that analyzes the source code to compute snapshots.
Database	| Stores configuration and snapshots.
Server |	Web interface that is used to browse snapshot data and make configuration changes.

![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/0c235ec0-5113-4078-b97e-2c51155a467d)

3. Prerequisites:
  1. A 64-bit system.
  2. A Java runtime environment: 
Oracle JRE or OpenJDK.
Minimum version: Java 17.  https://www.oracle.com/java/technologies/downloads/#jdk17-windows

4. Download SonarQube and Sonar Scanner
SonarQube :https://www.sonarsource.com/products/sonarqube/downloads/
Sonar Scanner:https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/scanners/sonarscanner/
![image](https://github.com/glitterzhang/SonarQube_postgresql_windows/assets/16975192/0ee7d0a2-362a-4287-9ac5-f00391e58802)

5. Download postgreSQL
https://www.postgresql.org/download/windows/

6. Connect SonarQube with PostgreSQL
  create database in PostgreSQL:sonar 
  create a user in PostgreSQL:sonar pw: 1234
 in directory "c:\Users\xx\sonarqube-10.5.1.90531\conf"
set
**  sonar.jdbc.url=jdbc:postgresql://localhost/sonar?currentSchema=public
  sonar.jdbc.username=sonar
  sonar.jdbc.password=1234**
7. Load SonarQube
   click **StartSonar.bat** under "C:\Users\xx\sonarqube-10.5.1.90531\bin\windows-x86-64\"

8. Create Project
