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
  图片修改：此电脑--本地磁盘（C:）--用户--用户名--docs--docs--images--api_legend--将自己做的图片增加到api_legend文档中（注意将图片名修改为任务名.png）

用路径在rst里面链接他.. image:: ../../images/api_legend/moveaxis.png
