# DOCKER TEMPLATE

## SERVICES

<ul>
    <li>PHP</li>
    <li>nginx</li>
    <li>MySQL</li>
    <li>PhpMyAdmin</li>
    <li>Node</li>
</ul>

## GETTING STARTED

### Clone repository
<code>git clone https://github.com/johnleosamante/docker-template.git</code>

### Rename project
<code>mv docker-template <em>app_name</em></code><br>
<code>cd <em>app_name</em></code>

### Create environment file
<code>cp .env.example .env</code>

### Edit .env file
<code># --- PROJECT ---</code><br>
<code>PROJECT_NAME=<em>app_name</em></code><br>
<code># --- DOMAINS ---</code><br>
<code>APP_DOMAIN=<em>appname.test</em></code><br>
<code>PMA_DOMAIN=<em>pma.appname.test</em></code><br>
<code># --- DATABASE CREDENTIALS ---</code><br>
<code>MYSQL_ROOT_PASSWORD=<em>strong_root_password</em></code><br>
<code>MYSQL_DATABASE=<em>app_database_name</em></code><br>
<code>MYSQL_USER=<em>app_database_user</em></code><br>
<code>MYSQL_PASSWORD=<em>app_database_password</em></code><br>
<code># --- PORTS ---</code><br>
<code>HTTP_PORT=80</code><br>
<code>HTTPS_PORT=443</code><br>
<code>MYSQL_PORT=3306</code>

### Install mkcert (Windows)
Open Admininstrator Powershell<br>
<code>choco install mkcert</code>

### Generate SSL Certificates
<code>mkcert -install</code><br>
<code>mkdir -p docker/nginx/ssl</code><br>
<code>cd docker/nginx/ssl</code><br>
<code>mkcert <em>appname.test</em> <em>pma.appname.test</em></code>

### Edit host file
c:/windows/system32/drivers/etc/hosts
Append to file
<code>127.0.0.1 <em>appname.test</em></code><br>
<code>127.0.0.1 <em>pma.appname.test</em></code>

### Start docker-compose
<code>docker-compose up -d --build</code>
