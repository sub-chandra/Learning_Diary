---
file_type: "Manual" 
file_catalogue: "Computer Science" 
Catalogue: 
  Main: "Linux"
  Secondary: "Grammar"
CreateTime: 2022
---

#Template/Knowledge/Manual/Main_Basic  
#Linux
>[!INFO] Introduction
>This page introduces the usage of the `Linux`


## Swap
> Swapping is the process whereby a page of memory is copied to the pre-configured space on the hard disk, called swap space, to free up that page of memory.

- Add the space for virtual memory
```shell
dd if=/dev/zero of=/swap bs=1024 count=1M  
mkswap /swap  
swapon /swap  
echo “/swap swap swap sw 0 0” >> /etc/fstab
```



## File
`cd`
### `ls`
`ls -a` : list all file and fold

### Create
`mkdir`: to make a fold
[Linux创建文件的5种方式 - zicmic - 博客园 (cnblogs.com)](https://www.cnblogs.com/zicmic/p/13097089.html)
```bash
touch
vim
echo $PATH > test.ini
cat 
```
### `mv`  
move the file
```bash
	mv <original name/addr> <new name/addr>
	mv <addr/file> <addr2>
	mv <addr1_file> <addr2/>
```

```bash
# add port  
firewall-cmd --zone=public --add-port=8080/tcp --permanent  

# reload the setting
firewall-cmd --reload

# Query the port
firewall-cmd --list-all  
firewall-cmd --list-ports
```


`htop`

