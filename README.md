![Alt text](harp.png?raw=true "Harp Framework")
# About Harp
[en_US]
Harp is a framework that has as its main feature to be multi-applications, that is, instead of always creating a project for an application, Harp allows you to create multiple applications and run them in a single instance of the project in a very simple way.

Let's say you have created two apps:

1 - MyWebApp
2 - MyApi

to access your applications just type in any browser: http://mydomain.com/MyWebApp or http://mydomain.com/MyApi and that's it!

Need a multi-application and heavily modularized framework? Harp may be your solution.

[pt_BR]
O Harp é um framework que possui como sua principal caractéristica ser multiaplicativos, ou seja, ao  invés de sempre criar um projeto para um aplicativo, o Harp te possibilita criar múltiplos aplicativos e rodar eles  em uma única instância do projeto de maneira muito simples.

Vamos supor que você tenha criado dois app's:

1 - MyWebApp
2 - MyApi

para acessar seus aplicativos basta digitar em um navegador qualquer: http://meudominio.com/MyWebApp ou http://meudominio.com/MyApi e pronto!

Precisa de um framework multiaplicativos e fortemente modularizado? Harp pode ser sua solução.

# Routes

[en_US]
Conventions:

When manually creating your routes in the routes json file keep in mind a few things:

The App name must be in PascalCase ex: AppBase, HelloWorld and etc.

The default route name must be written in lower ex: appbase, helloworld. The default route is a route with the same name as the app where typing http://mydomain.com/AppBase will run the appbase route.

Routes have several settings that can be seen in the following documentation: {{url_documentation}}

[pt_BR]
Convenções:

Ao criar manualmente suas rotas no arquivo routes json tenha em mente algumas coisas:

O nome do App deve ser em PascalCase ex: AppBase, HelloWorld e etc.

O nome da rota padrão deve ser escrita em lower ex: appbase, helloworld. A rota padrão é uma rota com o mesmo nome do app onde ao digitar http://meudominio.com/AppBase a rota appbase será executada.

As rotas possuem diversas configurações que poder ser vistas na seguinte documentação: {{url_documentação}}

# Encryption Keys

[en_US]
The keys by default are stored in storage/keys, when creating an application using the {playh} utility the key is generated automatically, if you want to generate the keys or change the keys you can run the following playh commands:

php playh build:key --app{appName} --force={true|false}

Manually via cmd or terminal:

navigate to: app/{appName}/storage/keys and run the following command:

php -r 'file_put_contents("encryption.key",base64_encode(random_bytes(32)));'

then run: chmod 0644 encryption.key

[pt_BR]
As chaves por padrão são guaradados em storage/keys, ao criar uma aplicação usando o utilitário {playh} a chave é gerada automaticamente, caso queira gerar as chaves ou alterar as chaves você pode executar os seguintes comandos playh:

php playh build:key --app{appName} --force={true|false}

Manualmente pelo cmd ou terminal:

navegue até: app/{appName}/storage/keys e execute o seguinte comando:

php -r 'file_put_contents("encryption.key",base64_encode(random_bytes(32)));'

depois execute: chmod 0644 encryption.key

# Certs

[en_US]
The keys by default are stored in storage/certs, when creating an application using the {playh} utility the certificate is generated automatically, if you want to generate the certificate or change it you can run the following playh commands:

php playh build:cert --app{appName} --force={true|false}

Generating a certificate for your application

navigate to: app/{appName}/storage/certs and run the following command:

openssl genrsa -out private.key 2048

or if you prefer a certificate with a password:

openssl genrsa -aes128 -passout file:../keys/encryption.key -out private.key 2048

then run: chmod 0644 private.key

[pt_BR]
As chaves por padrão são guaradados em storage/certs, ao criar uma aplicação usando o utilitário {playh} o certificado é gerado automaticamente, caso queira gerar o certificado ou alterá-lo você pode executar os seguintes comandos playh:

php playh build:cert --app{appName} --force={true|false}

Gerando um certificado para sua aplicação

navegue até: app/{appName}/storage/certs e execute o seguinte comando:

openssl genrsa -out private.key 2048

ou se preferir um certificado com senha:

openssl genrsa -aes128 -passout file:../keys/encryption.key -out private.key 2048

depois execute: chmod 0644 private.key


