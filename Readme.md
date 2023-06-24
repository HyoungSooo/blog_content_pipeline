# Blog content auto create, refactoring pipeline
This is a simple pipeline that creates or refactors blog posts and automatically uploads them.
You must have a personal blog to use this pipeline.
If not, use this project https://github.com/HyoungSooo/Django-Blog
The pipelines written here are all based on the projects above.

### linked with blog
If you have a personal blog, you need a login, create post api.

If not you can use sample blog project in https://github.com/HyoungSooo/Django-Blog

in that project have create post api, user create api, user login api using JWT

All of the code below is from the above blog project.

If you want to use your personal blog you need to modify the code.


### Usage
```shell
docker-compose -f docker-compose.yml up
```

Connect to http://localhost:8888/

upload pipeline.ipynb file to jupyter server

and run the fuctions

### Blog project in local
If the environment to deploy the blog is not available, you can take advantage of this pipeline by modifying the docker-compose.yml file.

in docker-compose.yml
```docker
...
  web:
      build: 
        context: <your docker file path>
      command: python manage.py runserver 0.0.0.0:8000
      ports:
        - "8000:8000"
      volumes:
        - <django app path>:/usr/share/web

      networks:
        - elk
      depends_on:
        - elasticsearch
...
```

### demo site
https://port-0-djangoblog-1duf6sd2blhjy1sm5.sel4.cloudtype.app/

### futuer works
* combine to Tiwwter, other blog api
* using cron to automatically run the pipeline
