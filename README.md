# LagabusComposition

## mongodb配置用户

1.  以admin启动mongo
    
`docker exec -it <container_name> mongo admin`

2.  创建管理者

`db.createUser({ user: <username>,pwd: <password>, roles: [{ role: 'userAdminAnyDatabase', db:'admin' }] })`

3.  退出mongodb并重新进入容器创建数据库用户 

`db.auth(<admin_username>,<admin_pwd>)`

4.  创建访问指定数据库的用户

`use <database_name>`

`db.createUser({ user: <username>,pwd: <password>, roles: [{ role: 'readWrite', db:'<database_name>' }] })`