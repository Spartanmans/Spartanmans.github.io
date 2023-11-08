+++
title = 'hugo papermod 部署问题丨上传GitHub page后无法显示CSS样式'
tags = [ "网站" ]
series = [ "网站" ]
date = 2023-11-7T16:00:51+08:00
draft = false

+++
问题挺多的，尤其是上传到GitHub这个流程，不过大多很快就搜出解决方法来了。最坑的就是上传成功后，访问网站无法正常显示CSS样式，F12提示报错“Failed to find a valid digest in the 'integrity' attribute for resource”。

最后是在这个[stackoverflow](https://stackoverflow.com/questions/65040931/hugo-failed-to-find-a-valid-digest-in-the-integrity-attribute-for-resource) 的回答里找到解决方法。

将以下代码添加到hugo.yml文件，再次上传就正常显示了。
yml：
--- params:
    assets:
        disableFingerprinting: true ---

toml:
--- [params.assets]
disableFingerprinting = true ---
