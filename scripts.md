### C

Compilar o arquivo:
gcc c/test.c -o c/test

Executar o arquivo:
c/test

### C++

Compilar o arquivo:
g++ cpp/test.cpp -o cpp/test

Executar o arquivo:
cpp/test

### Java

Compilar o arquivo:
javac java\*/Teste.java

Executar o arquivo:
java java\*.Teste

Baixe as extensões para Java do VSCodium e execute os testes automatizados.

### Node.JS

Instalar versão mais nova do Node.JS (18.x):
sudo apt-get install -y ca-certificates curl gnupg
mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
NODE*MAJOR=18
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node*$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
sudo apt-get update
sudo apt-get install nodejs -y

Executar o arquivo:
node nodejs/teste.js

Instalar o Jest:
sudo npm install -g jest
npm test

### PHP

Iniciar MySQL e Apache:
sudo service mysql restart
sudo service apache2 restart

Colocar arquivo PHP na pasta do Apache:
sudo mkdir /var/www/html/teste_php
sudo cp ./apps/php/php_info.php /var/www/html/test_php/

Executar o arquivo:
colocar no browser -> http://localhost/teste_php/php_info.php

Testar conexão com banco de dados:
sudo mysql
CREATE DATABASE example_database;
CREATE USER 'example_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
GRANT ALL ON example_database.\* TO 'example_user'@'%';
exit
mysql -u example_user -p
senha 'password'
CREATE TABLE example_database.my_list (my_id INT AUTO_INCREMENT, content VARCHAR(255), PRIMARY KEY(my_id));
INSERT INTO example_database.my_list (content) VALUES ("Item1");
sudo cp ./apps/php/my_list.php /var/www/html/test_php/

Executar o arquivo:
colocar no browser -> http://localhost/teste_php/my_list.php

Parar os serviços:
sudo service mysql stop
sudo service apache2 stop
sudo systemctl disable apache2.service
sudo systemctl disable mysql.service

### Ruby

Instalar Ruby com rbenv:
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
rbenv install ruby 3.0.2
rbenv global 3.0.2
echo "gem: --no-document" > ~/.gemrc
gem install bundler
gem env home

Instalar Rails:
gem install rails -v 7.0.7.2

Executar arquivo:
ruby ruby/test.rb

Executar Rails:
cd ruby/rails/blog
rails server

### Python

Executar arquivo:
python python/test.py

Instalar Django:
sudo pip install Django==4.2.4

Executar Django:
python python/django/mysite/manage.py runserver
