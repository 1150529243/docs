### vitepress

    前身是vuepress

vuepress vitepress rspress 静态站点生成器 Static Site Generator (SSG)

作用于项目 (博客，营销页面，档案，文档)

    安装

    ```sh
    npm i vitepress -D
    ```

    使用
    ```sh
    npx vitepress init  (启动.bin目录下的文件)

    ### vitepress 特有的formatter
    规则：必须是三个-  必须是写在头部

    ```js
    prev:
    ---
        text:'上一页 ： Runtime API'
        link: /markdown-examless1
    ---

    next:
    ---
    text:'下一页 ： Runtime API'
    link: /markdown-examless1
    ---
    ```

config 配置项 docFooter:'文档页脚'

### SEO(搜索引擎优化)

    面试回答  TDK （title description keywords）
    爬虫机器人会抓去网站的这三个值

    ```js
    ---
        outline: deep
        prev:
        text: "上一页：Runtime API"
        link: /markdown-examples
        head:
        - - meta
            - name: title
            content: Runtime API Examples
        - - meta
            - name: description
            content: Examples of using the runtime APIs provided by vitepress
    ---
    ```
    在加上head会提升SEO

    seo
    h1标签只能出现一个
    main标签只能出现一个
    img标签里面  alt和tiele必须有值  以为在网站搜索图片的时候会根据这个值来提取的
    a标签的href  里面写的东西很多 一定要写的  很重要  比如href有值 会调到那个网站查找
    其他的seo优化 就交给“金钱”了  因为花钱可以提升排名的

### 文章最后更改时间 lastUpdated

    这个必须配合git才有效  git提交这个文件的时间   就会被列为最后修改时间

    ```js
    lastUpdated: {
      text: "最后修改时间",
      formatOptions: {
        dateStyle: "full",
        timeStyle: "short",
      },
    },
    ```

### 搜索 全文检索

    ```js
    search: {
      provider: "local",
    },
    ```

## 贡献者

    vitepress是有插件可以编写vue代码的 写在对应的md文件就行

    ```js
    
    <script setup>

    import {VPTeamMembers} from 'vitepress/theme'

    const members = [
    {
        name:'VitePress',
        title:'core team',
        avatar:'http://vitejs.dev/logo.svg',
        link:'http://vitejs.dev/'
    }
    ]
    </script>

    <VPTeamMembers size="small" :members="members"/>
    ```

### 部署静态网站
    1.打开仓库的settings
    2.点击pages
    3.选择branch
    4.选择分支 选择项目  点击Save


### 如何访问
    在就 仓库的settings--点击pages 有链接显示
    项目地址 https://1150529243.github.io/docs/
