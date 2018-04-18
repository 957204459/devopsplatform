#将文件部署至salt并同步到客户端获取服务器信息

# 服务端创建_grains目录
mkdir /srv/salt/_grains
cp ./get_server.py  /srv/salt/_grains

# 同步
salt '*' saltutil.sync_all

# 获取
salt '*' grains.item used_memory