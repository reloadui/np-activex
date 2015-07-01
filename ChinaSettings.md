1.4.0以后已集成这些设置

## 银行网站 URL ##
支付宝官方已经提供支持。
最新支持农业银行，需更新兼容脚本。感谢 `@偌风之上_xys` 的帮助。

工商银行U盾用户、农业银行、中国银行、招商银行请在本站的<a href='http://code.google.com/p/np-activex/downloads/list'>下载区</a>下载相应的兼容补丁。后续版本将集成这些补丁。

以下为各网银的URL匹配模式。请根据需要添加。
```
https://*.icbc.com.cn/* ### 中国工商银行（需下载相关脚本）
https://*.cmbchina.com/* ### 中国招商银行（需下载相关脚本）
https://ebs.boc.cn/*  ### 中国银行(需在Download页面中下载相应插件）
https://*.abchina.com/*  
https://*.95599.cn/*    ### 中国农业银行（最新支持，需两者都添加，并下载相关脚本）
https://*.ecitic.com/*  ### 中信银行
https://*.cebbank.com/* ### 光大银行
https://*.95559.com.cn/* ### 交通银行 （暂无法使用）
https://*.sdb.com.cn/*  ### 深圳发展银行
https://*.ccb.com.cn/*  ### 建设银行
https://*.psbc.com/*  ### 邮政储蓄
```

## CLSIDs of plugins ##
```
{F3D0D36F-23F8-4682-A195-74C92B03D4AF}  ### 快播QvodPlayer
{22d6f312-b0f6-11d0-94ab-0080c74c7e95}  ### Windows Media Player
```

## 仍不能使用的，请在<a href='http://code.google.com/p/np-activex/issues/list'>此处</a>提交。 ##