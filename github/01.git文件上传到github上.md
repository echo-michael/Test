# <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git文件上传到github上</span>



## <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>1.安装git</span>

https://git-for-windows.github.io/

## <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>2.查看GitBash安装成功命令</span>

1. 打开Git Bash进入操作界面

2. <span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>查看github网站上账户名</span>

   <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git config --global user.name</span>

   <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git config --global user.email</span>

3. <span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>查看github上注册邮箱</span>

   <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git config --global user.email</span>

## <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>3.Git项目上传github</span>

<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>1.git仓库创建</span>

- 填写Reponsitory name-
- 选择public
- 勾选 Intialize this respository with a README
- Create Reponsitory

<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>2.文件上传</span>

新建上传项目->右键选中Gitbash here

<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>3.查看当前状态</span>

<span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git status</span>

把github上面的仓库克隆到本地

git clone  https://github.com/qwue/Test.git

上传项目拷贝到下载的新文件Test内

<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>4.将Test文件夹内容添加进来</span>

<span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git add  . </span>

<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>文件标记</span>

<span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git commit -m “提交信息” </span>

<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>5.将文件上传到github上</span>

<span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git push -u origin master</span>

问题总结：

![image-20200926155931317](upload\image-20200926155931317.png)

遇到以上问题，请使用<span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>git pull --rebase origin master</span>r进行本地和github仓库数据同步



