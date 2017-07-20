# Shared目录说明

```
src/shared
```

Shared目录主要包含以下几大类信息

* `cn`：中文语言包，和`lg.js`配合使用，全局配置中会配置对应的语言目录；
* `icon`：图标包，和`icons.js`配合使用，目前仅包含一套extjs中使用的个性化图标信息；
* `global.less`：CSS全局配置，之中包含了颜色定义、字体定义、可共享的全局CSS定义等【特别是颜色信息，所有的颜色信息都保存在global.less中，最后的应用呈现的“风格”依赖于该文件中定义的全局色彩、字体等】
* `actions.js`：Redux专用的Action定义文件；
* `routes.js`：Redux-Router使用的入口路由文件；
* `state.json`：应用专用初始状态格式文件，Redux中非OOB状态的专用数据状态文件；
* `uris.js`：远程API全局管理文件，用于管理所有远程的API路径信息，可支持表达式格式；

这些配置的典型特征：

* 每次添加一个新页面，这些内容都可能会被更改；
* 每个新页面改动的位置是一致的，不会因为逻辑不同而有所变更；
* 全局资源文件也会存放在该目录中；

## 1. Shared连接入口

```
src/lib/index.js
```

该文件为统一工具目录，之中包含的资源文件如下：

```javascript
import Lg from '../shared/lg.js'
import Types from '../shared/actions'
import Uri from '../shared/uris'
import Icon from '../shared/icons'

...
export default {
    ...
    // 共享资源文件
    Lg,
    Types,
    Uri,
    Icon: Icon.ExtJs,
}
```


