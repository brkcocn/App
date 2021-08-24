win10 启动U盘制作 

Universal MediaCreationTool  https://gist.github.com/AveYo/c74dc774a8fb81a332b5d65613187b15

### win10 企业版激活

```bash
以管理员身份打开CMD命令行窗口;

依次输入：

slmgr/ipk NPPR9-FWDCX-D2C8J-H872K-2YT43

slmgr/skms kms.03k.org

slmgr/ato
```

密匙

```bash
VK7JG-NPHTM-C97JM-9MPGT-3V66T

NPPR9-FWDCX-D2C8J-H872K-2YT43

VK7JG-NPHTM-C97JM-9MPGT-3V66T

W269N-WFGWX-YVC9B-4J6C9-T83GX

MH37W-N47XK-V7XM9-C7227-GCQG9

NYW94-47Q7H-7X9TT-W7TXD-JTYPM

NJ4MX-Vqq7Q-FP3DB-VDGHX-7XM87
```

win关闭FN FN+esc

win10  win+r->services.msc->Windows updata”选项，点击进入后选择“禁用”

 



 组策略gpedit.msc  改变通知



删除任务栏图标

“regedit” 然后打开如下键值：
 　HKEY_CLASSES_ROOT\Local Settings\Software\Microsoft\Windows\CurrentVersion\TrayNotify
 　在右边你可以看到两个键值；
 　IconStreams和PastIconsStream，将它们的值删除。



### vscode

关闭受限区信任：security.workspace.trust.enabled

关闭右侧缩略图 ：editor.minimap.enabled

code损坏是安装了 background的原因。

解决方法 安装Fix VSCode Checksums插件 ctrl+shift+p  fix->apply



### office 

office2019 专业增强版

下载地址 http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/media/zh-cn/ProPlus2019Retail.img

密匙 W8W6K-3N7KK-PXB9H-8TD8W-BWTH9 

Word

取消审阅 右键-->自定义功能区->校对

