# alfred-workflow-youdao
Alfred的有道翻译插件  
### 安装有道查询依赖（node.js）
```
  // 安装node.js
  sudo brew install node
  sudo brew install npm
  // 安装有道查询
  git clone https://github.com/easonjim/yddict.git
  npm install
  npm install . -g
  // 去除有道的查询提示
  vi ~/.config/configstore/yddict.json
  // 修改spinner为false，如果没有则使用这个JSON
      {
        "color": "white",
        "spinner": false
      }
  // 安装Alfred插件，直接双击youdao.alfredworkflow导入即可，导入之后再Alfred的Workflows中打开即可查询源码。
```
### 原理
1、先用node.js查询出结果  
2、输出一段Alfred能识别的XML  
```
<?xml version="1.0" encoding="utf-8"?>
<items>
  <item valid="yes">
      <title>10.0.2.11</title>
      <subtitle>45.76.65.119 美国新泽西州皮斯卡特维 choopa.com</subtitle>
      <icon>Info.icns</icon>
      <arg>http://www.baidu.com</arg>
  </item>
</items>
Alfred上每一行显示对应一个item，如果显示多行，那就在items下放入多个item即可
valid 表现为可不可以选择，点击，再次传递
title 主标题
subtitle 副标题
icon 图标
arg 跳转URL
```  
### 效果
![有道查询效果](https://github.com/easonjim/alfred-workflow-youdao/blob/master/effect/image.jpg?raw=true)
