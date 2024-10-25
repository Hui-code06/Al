# pr提交详细过程  
pr（pull request拉取请求）参考资料：[文档贡献指南](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/dev_guides/docs_contributing_guides_cn.html)  

1.**Fork**  
  先跳转到 [PaddlePaddle/docs](https://github.com/PaddlePaddle/docs) GitHub首页，然后单击 Fork 按钮，生成自己仓库下的目录，在浏览器上方复制下自己的链接，比如你的 GitHub 用户名为 USERNAME，则生成： https://github.com/USERNAME/docs。
  ![docs-contributing-guides-fork-repo](https://github.com/user-attachments/assets/9e128f1e-4533-489b-9b67-75c99e80f9e5)  

2.**Clone**
  将你目录下的远程仓库 clone 到本地，打开终端（Windows系统：win+R--cmd--回车）  
  `git clone https://github.com/USERNAME/docs`（此处粘贴刚刚复制的链接）  
  `cd docs`  

3.**创建本地分支**
  使用 `git checkout -b` 创建并切换到新分支。  
   `git checkout -b my-cool-stuff`  
  注意：在你使用 git checkout 切换到另一个分支之前，确保当前分支的工作目录是干净的（也就是说，没有未提交的更改或未跟踪的文件），可以通过运行 git status 命令来检查当前目录的状态，确保没有未提交的更改或未跟踪的文件。如果工作目录不干净，切换到新分支时，未跟踪的文件可能会被带到新分支上，这可能导致不必要的混乱或问题。

4.**安装pre-commit工具**  
  `pip install pre-commit==2.17.0`  
  `pre-commit install`  

5.**正式修改文档**  
  dst文档：此电脑--本地磁盘（C:）--用户--用户名--docs--docs--api--paddle--寻找在任务三领取的任务文档  
  在参数上方编辑一段简短清晰的文字说明，并用路径在rst中链接图片即输入以下代码:  
  `.. image:: ../../images/api_legend/任务名.png`  
  `  :width:600` （根据自身情况调节）  
  `  :alt: 图例`  
  图片修改：此电脑--本地磁盘（C:）--用户--用户名--docs--docs--images--api_legend--将自己做的图片增加到api_legend文档中（注意将图片名修改为任务名.png）  

6.**提交更改**  
  `git add docs/api/paddle/tile_cn.rst`  
  `git commit -m"add tile.png"`  

7.**推送分支**  
  将分支推送到Github  
  `git push origin 新分支名`  
  在倒数第二行会出现一个网页链接，复制到浏览器打开，点击pull request--new pull request--compare中勾选新分支--create pull request  
  
  注意！Github拒绝使用账号密码，需要密钥（点击Github个人头像--settings--developer settings--personal access tokens--fine-grained tokens）  
  ![Cache_-255d773934bb6697](https://github.com/user-attachments/assets/04caafb0-f399-4c47-a4c9-2646faf38da8)  
  ![Cache_-1a11170db5bbd6d8](https://github.com/user-attachments/assets/be8c2ac4-6492-48a8-ae3f-4e36d44f5641)

8.**提交**  
  按照下图格式提交
  ![image](https://github.com/user-attachments/assets/ed17b611-260f-447c-b80a-b130aa30aa36)

