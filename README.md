> 本项目基于 [Millennial主题](https://github.com/LeNPaul/Millennial)（作者：[Paul Le](https://lenpaul.com/)）创建，遵循 [MIT License](LICENSE.md) 进行修改和分发。

## 许可协议
本仓库包含的原始代码遵循 [MIT License](LICENSE.md)，修改部分同样适用该许可。第三方资源授权声明：
- 图标库：Font Awesome ([CC BY 4.0](https://fontawesome.com/license))
- 示例图片：[Death to Stock Photo](https://deathtothestockphoto.com/) 授权

### 鸣谢
- 原始开发者：[Paul Le](https://github.com/LeNPaul)  

```
ZenBlog
├─ 404.md                    # 404错误页面内容（Markdown格式）
├─ assets                    # 静态资源目录
│  ├─ css                    # CSS样式文件
│  │  ├─ main.css            # 编译后的主样式文件
│  │  ├─ main.css.map        # Sass编译源映射文件（用于调试）
│  │  ├─ main.scss           # Sass主入口文件（定义全局样式）
│  │  └─ syntax.css          # 代码块语法高亮专用样式
│  └─ img                    # 博客图片资源
│     ├─ arctic-1.jpg        # 示例文章相关图片
│     ├─ arctic-2.jpg        # ...
├─ favicon.ico               # 网站图标
├─ Gemfile                   # Ruby依赖管理文件（Jekyll插件声明）
├─ index.html                # 博客首页HTML模板
├─ LICENSE.md                # 项目许可证文件
├─ package.json              # npm项目配置（前端依赖/脚本命令）
├─ package-lock.json         # 精确npm依赖版本锁定文件
├─ pages                     # 自定义页面集合
│  ├─ about.md               # "关于我们"页面内容
│  ├─ contact.md             # 联系信息页面
│  ├─ documentation.md       # 文档说明页面
│  ├─ facts.md               # 数据/统计信息展示页面
│  └─ sample-posts.md        # 示例文章说明页面
├─ README.md                 # 项目说明文档
├─ rss-feed.xml              # 自动生成的RSS订阅源
├─ _config.yml               # Jekyll核心配置文件（站点元数据）
├─ _data                     # 数据文件目录
│  └─ settings.yml           # 自定义配置数据（如导航栏设置）
├─ _includes                 # 可复用组件模板
│  ├─ disqus.html            # Disqus评论系统集成模板
│  ├─ featured-post.html     # 精选文章展示组件
│  ├─ footer.html            # 全站页脚模板
│  ├─ google-analytics.html  # Google Analytics跟踪代码
│  ├─ head.html              # HTML头部模板（包含meta/css链接）
│  ├─ header.html            # 导航栏/页眉模板
│  ├─ post-date.html         # 文章日期显示组件
│  ├─ post-share.html        # 社交媒体分享按钮组件
│  └─ related-posts.html     # 相关文章推荐组件
├─ _layouts                  # 页面布局模板
│  ├─ category.html          # 文章分类页面布局
│  ├─ default.html           # 基础布局模板（其他布局继承此模板）
│  ├─ home.html              # 首页专用布局
│  ├─ page.html              # 普通页面布局（如关于/联系页面）
│  └─ post.html              # 文章详情页布局
├─ _posts                    # 博客文章集合
│  ├─ 2016-04-04-about-the-author.md  # 按Jekyll规范命名的文章
│  ├─ 2016-05-05-learning-resources.md # ...
├─ _sass                     # Sass样式模块
   ├─ _base.scss             # 基础样式（重置/排版规则）
   ├─ _code.scss             # 代码块样式定制
   ├─ _footer.scss           # 页脚专用样式
   ├─ _header.scss           # 导航栏/页眉样式
   ├─ _home.scss             # 首页特有样式
   └─ _variables.scss        # Sass变量定义（颜色/间距等）

```