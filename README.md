# dev_GoCDRH7
GoCD Deployment to RHEL 7.x

[GoCD Home](https://gocd.org)<br/>
Lstest version: 22.1.0 - Released 3/21/22<br/>
Download Server: [RedHat](https://download.gocd.org/binaries/22.1.0-13913/rpm/go-server-22.1.0-13913.noarch.rpm) <br/>
Download Agent: [RedHat Agent](https://download.gocd.org/binaries/22.1.0-13913/rpm/go-agent-22.1.0-13913.noarch.rpm) <br/>

Latest version: 20.10.0 - Released 11/23/20<br/>
Download: [RedHat](https://www.gocd.org/download/#redhat)<br/>

#### GoCD Documentation
- Pipelines
  [https://docs.gocd.org/current/gocd_on_kubernetes/sample_pipelines_explained.html](https://docs.gocd.org/current/gocd_on_kubernetes/sample_pipelines_explained.html) <br/>
- Cookiecutter
  [https://cookiecutter.readthedocs.io/en/1.7.0/README.html](https://cookiecutter.readthedocs.io/en/1.7.0/README.html) <br/>

#### GoCD vs. Jenkins
- [https://www.lambdatest.com/blog/jenkins-vs-gocd-battle-of-ci-cd-tools/](https://www.lambdatest.com/blog/jenkins-vs-gocd-battle-of-ci-cd-tools/) <br/>

#### Update
- latest Version 21.4.0
- Download: <br/>
  Server: [https://download.gocd.org/binaries/21.4.0-13469/rpm/go-server-21.4.0-13469.noarch.rpm](https://download.gocd.org/binaries/21.4.0-13469/rpm/go-server-21.4.0-13469.noarch.rpm) <br/>
  
  Agent: [https://download.gocd.org/binaries/21.4.0-13469/rpm/go-agent-21.4.0-13469.noarch.rpm](https://download.gocd.org/binaries/21.4.0-13469/rpm/go-agent-21.4.0-13469.noarch.rpm) <br/>

#### H2 Database Information
- [Quickstart](http://www.h2database.com/html/quickstart.html) <br/>
- [Download](http://www.h2database.com/html/download.html) <br/>

#### Postgres Repo Info
- Repo/RPM URLs Info
  [https://yum.postgresql.org/repopackages/](https://yum.postgresql.org/repopackages/) <br/>

- Required Postgresql13 Packages:
  - postgresql13
  - postgresql13-server
  - postgresql13-libs
  - postgresql13-contrib

- Build Base GoCD PostgresDB
  ```
  CREATE ROLE "gocd_database_user" PASSWORD 'gocd_database_password' NOSUPERUSER NOCREATEDB NOCREATEROLE INHERIT LOGIN;
  CREATE DATABASE "gocd" ENCODING="UTF8" TEMPLATE="template0";
  GRANT ALL PRIVILEGES ON DATABASE "gocd" TO "gocd_database_user";
  ALTER ROLE "gocd_database_user" SUPERUSER;
  ```
  
- RHEL 7 x86_64
  - [https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm](https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm) <br/>

- Posgresql13 DB
  - YUM:  postgresql13 postgresql13-server postgresql13-contrib (need for drivers)
  ![Postgresql Tables](https://github.com/lel99999/dev_GoCDRH7/blob/master/gocd_postgresql13-01.png) <br/>

- AD Related Notes: AD2016 Install LDAP Role
  - UserLoginFilter: (sAMAccountName={0})  
  - UserSearchFilter: (|(sAMAccountName=*{0}*)(uid=*{0}*)(cn=*{0}*)(mail=*{0}*)(otherMailbox=*{0}*))
  - DisplayNameAttribute: displayName/CN
  


