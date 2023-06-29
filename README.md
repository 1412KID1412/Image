# Image

用于保存markdown文件中的图片

需要注意  **信息脱敏处理**

# Typroa中PicGo-Core配置如下：

[一个PicGo重命名插件](https://github.com/liuwave/picgo-plugin-rename-file)

```json
{
  "picBed": {
    "current": "github",
    "github": {
      "repo": "用户名/仓库名",
      "branch": "分支名",
      "token": "",
      "path": "仓库中文件名/",
      "customUrl": ""
    }
  },
  "picgoPlugins": {
    // 根据时间对图片重命名
    "picgo-plugin-rename-file": true,
    "picgo-plugin-super-prefix": true
  },
  /**
  picgo-plugin-rename-file插件的命名规则
  {y} 年，4位
  {m} 月，2位
  {d} 日期，2位
  {h} 小时，2位
  {i} 分钟，2位
  {s} 秒，2位
  {ms} 毫秒，3位(v1.0.4)
  {timestamp} 时间戳(秒)，10位(v1.0.4)
  {hash}，文件的md5值，32位
  {origin}，文件原名（会去掉后缀）
  {rand:<count>}, 随机数，<count>表示个数，默认为6个，示例：{rand：32}、{rand}
  {localFolder:<count>}, <count>表示层级 ，默认为1，示例：{localFolder:6}、{localFolder}

  设置路径格式为：
  fix-dir/{localFolder:2}/{y}/{m}/{d}/{h}-{i}-{s}-{hash}-{origin}-{rand:6}
  上传的文件将会被重命名为：
  fix-dir/images/test/2020/07/24/21-40-31-36921a9c364ed4789d4bc684bcb81d62-localImage-fa2c97.jpg
  */
  "picgo-plugin-rename-file": {
    "format": "{y}/{m}/{d}/{hash}-{rand}"
  }
}
```
