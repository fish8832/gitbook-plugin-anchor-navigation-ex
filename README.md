Math integration with GitBook
==============

### en
Add TOC to the side of the side of the suspension navigation. Optional: sort and rewrite the page title
 * 1. based on  https://github.com/zhangzq/gitbook-plugin-navigator
 * 2. based on https://github.com/yaneryou/gitbook-plugin-anchor-navigation
 * 3. bug Restore 2 invalid does not display the bug
 * 4. The plug-in dependency Plug in,https://plugins.gitbook.com/plugin/anchors  @Latest: 0.7.1+ so the anchors plug-in must be before the plug-in
 * 5. If you don't have a h[1-3] tag on the page, you will not generate and replace any headers

### cn
添加toc到侧边悬浮导航。可选：排序并重写页面标题.
本插件修改源插件的功能：综合修复了原有的bug和兼容性,本插件没有业务逻辑，在编译时被调用
 * 1. 基于 https://github.com/zhangzq/gitbook-plugin-navigator
 * 2. 基于 https://github.com/yaneryou/gitbook-plugin-anchor-navigation
 * 3. 修复 bug ：gitbook-plugin-anchor-navigation 不正常显示
 * 4. 该插件依赖 https://plugins.gitbook.com/plugin/anchors @Latest: 0.7.1+ 插件，所以 anchors 插件的必须在本插件之前被安装到book.json中
 * 5. 页面如果缺少h[1-3]标签，那么不会生成和替换任何标题

### Be careful
#### en
To properly generate navigation, follow these levels
|- H1
|--h2
|---h3
The wrong way:
|--h2
|---h3

#### cn
想要正确生成导航，请按照以下层级
|- h1
|--h2
|---h3
错误的写法是：
|--h2
|---h3
也就是说，一般我们都会按照层级来书写。

### Sample
 https://zq99299.gitbooks.io/gitbook-guide/content/chapter/plugin.html
 
 ![image](https://raw.githubusercontent.com/zq99299/gitbook-plugin-anchor-navigation-ex/master/doc/images/gitbook-plugin-anchor-navigation-ex-demo2.jpg)
 ![image](https://raw.githubusercontent.com/zq99299/gitbook-plugin-anchor-navigation-ex/master/doc/images/gitbook-plugin-anchor-navigation-ex-demo.jpg)



### How to use it?

Add it to your `book.json` configuration:

```
{
  "plugins": [
	   "anchors",
       "anchor-navigation-ex"
  ]
}
```

Install your plugins using:

```
$ gitbook install ./
``` 

### Configuration

You can force the use of svg pre-processed by adding to your book.json:

```
{
 "pluginsConfig": {	   
		"anchor-navigation-ex":{
			"isRewritePageTitle":true
		}	   
  }	
}
```
 

isRewritePageTitle :
* en : Do you want to overwrite the page title, true: will overwrite the anchors plug-in anchor effect
* cn : 是否重写页面标题，true:将会覆盖anchors插件锚点效果

## or Install locally

```
$ npm install gitbook-plugin-anchor-navigation-ex --save
```

>open npm : https://www.npmjs.com/package/gitbook-plugin-anchor-navigation-ex

### Update record
#### 2017-01-18
* en : Page without h[1-3] tag generation failed
* cn : 页面没有h[1-3] 标签生成失败

#### 2017-01-22
* en : 2017-01-18 fix bug
* cn : 2017-01-18 提交的有问题。重新修复