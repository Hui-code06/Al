# Windows下从源码编译可能遇到的问题
1. 注意下载VS2019版本；  
  
2. 克隆仓库遇到网络限制、不稳定网络连接时，使用镜像源；  
   ![Cache_53ca44059f5f5e74](https://github.com/user-attachments/assets/04ada997-5b8d-463f-adfe-c81f075dec50)
   可使用https://ghp.ci/+链接（格式如下） 或询问GPT
   ![Cache_1f2e6d00d5ccf1fd](https://github.com/user-attachments/assets/ba665359-8154-44fc-b757-005f9de03725)  

3.配置cmake时遇到网络问题；  
   ![IMG_20241017_231606](https://github.com/user-attachments/assets/568308a0-795a-40ce-b017-95036389b3e7)
   尝试1.更改IP  <a href="https://cloud.tencent.com/developer/article/2023920" title="更改IP教程">IP更改教程</a>  
   尝试2.卸载mingw后询问GPT怎么在命令中指定编译路径（指定64位编译器，能向下兼容）  
     删除后报错
     ![Cache_-1b6c1bf4f3d35036](https://github.com/user-attachments/assets/2ea41f39-1a22-44f8-aba4-59f8b4fa7069)
     ![qq_pic_merged_1729178848616](https://github.com/user-attachments/assets/0562ad08-ea25-4df8-b4cf-1620d4c18779)
     删除CMakeCache后重开。后cmake配置了两小时——timeout。  
     重开again——fatal: not a git repository: D:/workspace/Paddle/.git/modules/third_party/snappy
      Synchronizing submodule url for 'third_party/snappy'
      CMake Error at cmake/third_party.cmake:50 (message):
      Failed to sync submodule, please check your network !
      Call Stack (most recent call first):
      CMakeLists.txt:603 (include)
      报以上的Error（忘记截图了）  
    尝试3.（vpn把全局打开）先在命令行输入git config --global http.proxy http://your_proxy_address:your_proxy_port
      输入VPN地址和端口号，位置：打开梯子、打开系统代理设置，寻找服务地址。
    报错如下![Cache_345d9a2b8e9a4749](https://github.com/user-attachments/assets/92fe7950-7347-4e66-953f-f5f1483dbade)
    重新创建文件夹重走流程——发现环境变量没配置好输入（注意在父目录Paddle中运行）cmake . -B build -GNinja -DWITH_GPU=OFF -DPYTHON_EXECUTABLE="C:\python3.10\python.exe" -DPYTHON_INCLUDE_DIR="C:\python3.10\include" -DPYTHON_LIBRARY="C:\python3.10\libs\python310.lib"（寻找自己电脑对应的python路径）
    python路径寻找方法：win+R——输入cmd——where python （路径从C:开始）
    后删除重新下载python，安装python勾选时Add CMake to the system PATH for all users
    在经过多方尝试和小游oops的协助下终于cmake完成！！！
    增加时间戳timecmd.bat  

4.在ninja之前安装pip3.8 install -r ../python/requirements.txt（过不了加个镜像）
  ![Cache_50f5b9cc245bf1b8](https://github.com/user-attachments/assets/72142e67-5e84-4555-9f41-333c0545e4d5)
  （还未pip时报错）
  ![Cache_-6dbac6e60c934a1e](https://github.com/user-attachments/assets/d06d26c8-4040-4160-abe5-dbc0d6914df7)
  确定python版本——3.10，并保证目录正确（build目录中运行）
  成功后timecmd.bat ninja发现电脑配置不够换小游电脑继续，至成功！！！  

小游后来总结最关键的一步是：当你光报错的时候，删除paddle，重新克隆。



    
     
