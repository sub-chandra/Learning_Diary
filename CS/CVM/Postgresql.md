---
file_type: # Manual
file_catalogue:
CreateTime: 2022
---

#Missing 

https://github.com/Netflix/lemur/issues/2857

find /usr -name postgis.control


```bash
psql -U postgres -h localhost
postgres=> 
```

# Problem
## `Install postgresql-contrib`
The version of the `pgsql` and `contrib` should be same.
>Ref.
>[Linux 上PostgreSQL 12 pg_trgm扩展安装_小浩MR.C的博客-CSDN博客](https://blog.csdn.net/weixin_41070914/article/details/106670106?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_utm_term~default-0-106670106-blog-107653766.pc_relevant_multi_platform_whitelistv3&spm=1001.2101.3001.4242.1&utm_relevant_index=3)
>[pg_trgm postgresql插件安装 – ITGeeker技术奇客](https://www.itgeeker.net/pg_trgm-postgresql%e6%8f%92%e4%bb%b6%e5%ae%89%e8%a3%85/)

### Problem List
- $libdir/pg_trgm

```bash
yum install -y https://download.postgresql.org/pub/repos/yum/14/redhat/rhel-7-x86_64/postgresql14-contrib-14.2-1PGDG.rhel7.x86_64.rpm --skip-broken
```
yum remove -y postgresql* && rm -rf  /var/local/pgsql && rm -rf  /usr/pgsql* && userdel -r postgres && groupdel postgres


yum install postgresql postgresql-contrib postgresql-server -y

echo "export PATH=/usr/pgsql-14/bin:$PATH" >> /etc/profile

/usr/pgsql-10/bin/postgresql-10-setup initdb


yum list | grep postgresql

yum install postgresql postgresql-contrib postgresql-server -y

rpm -aq| grep postgres