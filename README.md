# Notes

## Configure a SonarQube Server Locally

### System Requirements
- **Java 17+** (Oracle JDK, OpenJDK, or AdoptOpenJDK)
- **Hardware Recommendations:**
  - Minimum 2 GB RAM
  - 2 CPU cores

### Installation Steps

1. Update system packages:
   ```bash
   sudo apt update && sudo apt install unzip -y
   ```

2. Create a SonarQube user:
   ```bash
   adduser sonarqube
   ```

3. Download SonarQube:
   ```bash
   wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.4.1.88267.zip
   ```

4. Extract the archive:
   ```bash
   unzip sonarqube-10.4.1.88267.zip -d /opt/
   ```

5. Set proper permissions:
   ```bash
   chown -R sonarqube:sonarqube /opt/sonarqube
   chmod -R 775 /opt/sonarqube
   ```

6. Start the SonarQube server:
   ```bash
   cd /opt/sonarqube/bin/linux-x86-64
   ./sonar.sh start
   ```

### Access SonarQube
Once started, access the SonarQube server at: `http://<ip-address>:9000`

🎉 Congratulations! Your SonarQube server is now running.