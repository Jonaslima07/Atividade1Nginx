# Tutorial de como criar a aplicação react e configurar para o nginx

## Etapa 1:
- primeiro você tem que ter o nginx instalado em sua máquina, para isso execute o seguinte comando:
```
sudo apt update
sudo apt install nginx
``` 
## Etapa 2:
- Escolha o projeto em qual você quer utilizar no servidor nginx, quando escolher, faça os seguintes passos:
```
git clone https://github.com/fulanodetal/ProjetoInovador.git
cd ProjetoInovador
```  
## Etapa 3:
- Instale as dependências:
```
npm install
```
# Etapa 4: 
- Execute o comando a seguir para deixar sua aplicação pronta para produção:
```
npm run build
```
# Etapa 5: 
- Copie os arquivos para a pasta do nginx:

```
sudo mkdir -p /var/www/procureaki
sudo cp -r dist/* /var/www/procureaki
```
# Etapa 6:
- Configure o nginx:
```
sudo nano /etc/nginx/sites-available/procureaki

```
- Cole a seguinte configuração:
```
server {
    listen 80;
    server_name;

    root /var/www/procureaki;
    index index.html;

    location / {
        try_files $uri /index.html; #Aqui resolve o problema da rota.
    }
}


```
- Logo apois, habilite o site com o comando:
  
```
sudo ln -s /etc/nginx/sites-available/procureaki /etc/nginx/sites-enabled/
```
# Etapa 7:
- Analise se deu tudo certo com o comando:
```
sudo nginx -t
```
- Se deu certo, reinicie o servidor com o comando:
```
sudo systemctl restart nginx
```
# Etapa 8:
- Logo após, execute o projeto em seu brower digitando: localhost  ou seu IP:
  
```
http://localhost
```
# Se tudo tiver correto, irá mostrar a aplicação assim por exemplo: 

![appBrowser](images/original.png)