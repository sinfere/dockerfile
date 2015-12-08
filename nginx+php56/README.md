# nginx + php56
Expose port 7001. 

Usage:

```
docker run -d --name="wordpress" -p 80:7001 -v /opt/htdocs:/opt/htdocs sinfere/wordpress
```

A good image for running wordpress, split execution environment and wordpress file
