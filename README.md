# iconfontcn

Kiss Iconfont.

### 安装 iconfontcn

```
npm install -g iconfontcn
```

### iconfontcn 有什么用

1. 简化 iconfont 的使用
1. 提供了更灵活的 Icon 组件

### iconfont 是什么？

阿里妈妈 MUX 倾力打造的矢量图标管理、交流平台，设计师将图标上传到 iconfont 平台，用户可以自定义下载多种格式的 icon，平台也可将图标转换为字体，便于前端工程师自由调整与调用。

### iconfont 的 Web 端使用方式

> https://www.iconfont.cn/help/detail?spm=a313x.7781069.1998910419.d8cf4382a&helptype=code

1. unicode 引用
1. font-class 引用
1. symbol 引用，全新的使用方式，未来的主流

### 通过 iconfontcn 使用 iconfont

1. 查看 iconfont 项目的 Font Family、FontClass/Symbol 前缀信息

   > iconfont.cn > 资源管理 > 我的项目 > 更多操作 > 编辑项目

1. 查看 iconfont 项目的 Font class/Symbol

   > iconfont.cn > 资源管理 > 我的项目 > Font class / Symbol

1. 项目 index.js 中初始化 iconfontcn（只需要初始化一次）

   ```
   import Iconfont from "iconfontcn";

   // init参数说明
   //Iconfont.init("Font class/Symbol地址", "FontClass/Symbol 前缀", "Font Family");

   // font-class引用
   Iconfont.init("font_2043983_voy5aew0vz.css", "t-", "testfont");

   // symbol引用
   Iconfont.init("font_2043983_voy5aew0vz.js", "t-");
   ```

1. Icon 组件属性和使用

   | 属性名    | 类型             | 说明                     |
   | --------- | ---------------- | ------------------------ |
   | code      | string           | 图标的代码               |
   | size      | number \| string | 图标的大小，优先级最高   |
   | color     | string           | 图标的颜色，优先级最高   |
   | style     | object           | 行内样式，优先级第二     |
   | className | string           | 外部引用 css，优先级第三 |

   ```
   import { Icon } from "iconfontcn";

   <Icon code="offer" size="18"/>
   ```

### 不通过 iconfontcn 加载 js 或 css，使用 Icon 组件

如果项目中使用本地资源或者在 index.html 中加载了 iconfont 的 css 或 js，也可以使用 iconfontcn 的 Icon 组件，需要在 index.js 中配置 iconfontcn（只需要配置一次），注意 iconfont 的引用方式。

```
import Iconfont from "iconfontcn";

// config参数说明
//Iconfont.config("i | svg", "FontClass/Symbol 前缀", "Font Family");

// font-class引用，第一个参数传 i
Iconfont.config("i", "t-", "testfont");

// symbol引用，第一个参数传 svg
Iconfont.config("svg", "t-");
```

```
import { Icon } from "iconfontcn";

<Icon code="offer"/>
```

> Hope you will like !
