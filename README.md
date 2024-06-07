# ⌨️ 雾凇输入法使用指南〔个人定制〕

![](https://gitee.com/justdoitor/gitee-images-plus/raw/master/images/202402120910811.jpg)

### 🔗 参考&链接

[👍作者 `GitHub` 仓库地址](https://github.com/iDvel/rime-ice)

[📄 小狼毫 `GitHub`仓库](https://github.com/rime/weasel)

[📄`Rime` 定制:官方文档](https://github.com/rime/home/wiki/CustomizationGuide#%E5%AE%9A%E8%A3%BD%E6%8C%87%E5%8D%97)

[📑`Rime` 配置说明 - 雾凇输入法文档](https://dvel.me/posts/rime-ice/)

[😊`emoji` 查询](https://www.emojiall.com/zh-hans)

[🎨小狼毫内置皮肤预览图](./own/内置皮肤预览图.png)

### ⬆️ 更新说明

﹝📅 2024年04月15日﹞

- 添加了个人自用词库﹝洛奇英雄传﹞相关的﹝`mabinogi_heroes_dicts`﹞文件夹及其文件夹下的词库文件；

- 添加了扩展词库相关的目录：📁 `extra_dicts` 其下添加了：
  - 搜狗词库官方「一人之下」词库

- 更新并调整默认「反查词库」为带音标的词库；

  `rime_ice.schema.yaml`

  ```yaml
  # 部件拆字滤镜
  radical_reverse_lookup:
    tags: [ radical_lookup ]
    # dictionary 为拼音标注来源。目前是显示本方案词库的注音，可去部件拆字方案下载更全的、带声调的、已编译好的词典
    # https://github.com/mirtlecn/rime-radical-pinyin?tab=readme-ov-file#%E5%8F%8D%E6%9F%A5%E5%B8%A6%E5%A3%B0%E8%B0%83%E6%B3%A8%E9%9F%B3
    dictionary: zdict # 提示码词表﹝汉典注音，无音者注 n/a（推荐）﹞
    # comment_format:     # 自定义 comment，例如在左右加上括号
    #  - xform/^/(/
    #  - xform/$/)/
  因为没有找到一份比较好的词库，干脆自己维护一个。综合了几个不错的词库，精心调教了很多。
  ```

📅 ﹝ 2024年06月07日 ﹞

- 启用在特定的程序中，开启始终使用英文标点符号（一般为开发工具应用程序）

  涉及到的文件：📄 `weasel.custom.yaml`，修改如下：

  ```yaml
  # 打补丁
  patch:
    # 设置样式
    "style/color_scheme": dark_temple                        # 设置主题配色
    "style/horizontal": false                         # 候选项横排：true；false
    "style/vertical_text": false                      # 竖排文本：true；false
    # 指定特定程序使用英文标点符号（⚠️ 应用程序名称一律使用小写字母）
    app_options/pycharm64.exe:  # PyCharm.
      ascii_punct: true
    app_options/typora.exe:  # Typora.
      ascii_punct: true
  ```
  
  可以操作的其它设置:
  
  - `ascii_mode: true`：默认英文
  - `ascii_mode: false`：默认中文
  - `ascii_punct: true`：开启英文标点
