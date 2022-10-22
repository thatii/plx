# plx
Nextcloud 配置 external-storage
首先需要配置 docker compose 文件中，nextcloud 下的volumes 属性，也就是添加mount 目录。将你需要映射的外部存储目录添加到这里，记得修改完成后，重启本 docker-compose 项目。
volumes:
    - /data/nextcloud:/var/www/html
    - /data:/data
    - /abc:/abc
在宿主机上执行命令 sudo chown -R www-data <abc> #<>这里是你需要修改的目录, 让Nextcloud 有权限读写、管理文件
打开 http://ip 使用你喜欢的任意密码进行登录
点击右上角 设置 -> 应用
启用 External storage support 插件, 并输入密码确认
plugin

点击右上角 设置 -> 管理 -> 外部存储 进行添加外部存储, Aria2 下载的文件会存在/data 目录下，存储类型选择本地存储，当存储添加成功，且可用时，最左端会显示出绿色。 Add external storage
搞定，现在你通过 AriaNg 下载的文件就可以在 Nextcloud 里面查看到了。
