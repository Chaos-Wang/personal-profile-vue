### 目录结构
    +blog                                               -blog
        +.nuxt                                              -nuxt用于实现路由
            -...
        +assets                                             -sass格式的静态资源
            -...
        +components                                         -封装的组件
            -Dialog.vue                                     -提示窗口
            -Footer.vue                                     -页脚
            -Header.vue                                     -页头
            -Loading.vue                                    -加载
            -LoadMore.vue                                   -加载新分页
            -Menu.vue                                       -菜单
            -Post.vue                                       -ACHIEVEMENTS页面中的Categories
            -Project.vue                                    -项目页面
            -SideMenu.vue                                   -侧边菜单
            -TimeLine.vue                                   -ACHIEVEMENTS页面中的TimeLine
        +layouts                                            -布局
            -default.vue                                    -布局
        +pages                                              -页面
            +post                                           -页面模板
                -_id.vue                                    -页面模板
            +search                                         -搜索组件与按分类归档
                +category                                   -按分类归档
                    -_id.vue                                -分类页面模板
                +keyword                                    -关键词检索
                    -_keyword.vue                           -关键词检索模板
            -aboutme.vue                                    -SideMenu AboutMe页面
            -archive.vue                                    -Achievements页面(包含归档和TimeLine)
            -index.vue                                      -访问首页
            -laboratory.vue                                 -Project页面
        +plugins
            -axios.js                                       -API请求封装
        +static                                             -资源
            -...
        -nuxt.config.js                                     -项目信息配置(title、keywords等)
        -package.js                                         -包管理
        -package-lock.js                                    -包管理
        
### 技术选型
 	    -vue.js
 	    -nuxt.js
 	    -scss
 	    -es6/7
        
### 部署指南
    1. clone本项目
    2. cd到项目目录并执行npm install
    3. 执行npm run dev(开发模式)或npm run build(上线部署)

### 访问地址（本地）：localhost:3000

### [后端](https://github.com/Chaos-Wang/personal-profile-backmanagement)
