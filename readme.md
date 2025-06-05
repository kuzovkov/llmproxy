### Run storage

```bash
docker-compose up -d
```
#### Get SSl certificates
rename nginx/conf.d/default-ssl.conf -> nginx/conf.d/default-ssl.conf.bak

```bash
mv nginx/conf.d/default-ssl.conf nginx/conf.d/default-ssl.conf.bak
mv nginx/conf.d/default.conf.bak nginx/conf.d/default.conf

./certbot.sh lmstudio.kuzovkov12.ru
./certbot.sh ollama.kuzovkov12.ru

mv nginx/conf.d/default-ssl.conf.bak nginx/conf.d/default-ssl.conf 
mv nginx/conf.d/default.conf nginx/conf.d/default.conf.bak
 
docker-compose restart nginx
```

Assigned that `LMStudio` listen on port `1234` and `Ollama` listen on port `11434`
Else make changes in `Nginx` configuration files.

LMStudio API:  `https://lmstudio.kuzovkov12.ru:4443/v1`

Ollama API `https://ollama.kuzovkov12.ru:4443/v1`

