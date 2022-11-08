# 部署步骤

## 编译
```shell
bundle install && bundle exec jekyll build
```

## 将资源文件复制到Nginx目录中
```shell
cp -r _site /var/www/html/_site
```

### Nginx配置
```shell
        root /var/www/html/_site;
        index index.html;

       location / {
		try_files $uri $uri/ =404;
       }
```