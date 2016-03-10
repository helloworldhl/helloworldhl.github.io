# Cannot proceed with delivery: an existing transporter instance is currently uploading this package  

>今天上传AppStore，网络原因中断了一次，重新上传遇到个报错，如标题。

### 原因 
**上传的动作被记录在UploadToken中了。**
把Application Loader(XCode->Organizer->Archived Applications->Submit)中正在上传的文件中断或者删除，再次Submit提示：
Cannot proceed with delivery: an existing transporter instance is currently uploading this package。
无论如何Clean All、重新Submit都失败，给出上述提示。

### 解决方法：
（1）打开终端，输入cd，到达个人用户目录下。

（2）输入ls -a，可以看到一个隐藏的目录 .itmstransporter

（3）cd .itmstransporter/UploadTokens

（4）ls ，可以看到一个类似xxxxx.local_itunesConnectUSERxxxxxx.itmsp.token文件

（5）nano  xxxxx.local_itunesConnectUSERxxxxxx.itmsp.token，在里面把内容都删除，保存。

（6）重新在Organizer里面submit，(๑˃́ꇴ˂̀๑)˂ᵒ͜͡ᵏᵎ⁾ 了


>或者终端中运行
>defaults write com.apple.finder AppleShowAllFiles -bool true
>显示隐藏文件，在个人用户目录中找到上述文件删除

