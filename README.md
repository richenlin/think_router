# 介绍
-----

[![npm version](https://badge.fury.io/js/think_router.svg)](https://badge.fury.io/js/think_router)
[![Dependency Status](https://david-dm.org/richenlin/think_router.svg)](https://david-dm.org/richenlin/think_router)

Router for ThinkKoa.

# 安装
-----

```
npm i think_router
```

# 使用
-----

1、router中间件为thinkkoa内置中间件,无需在项目中创建引用。该中间件默认开启

2、项目中间件配置 config/middleware.js:
```
config: { //中间件配置
    ...,
    router: {
        multi_modules: false, //开启多模块支持
        deny_modules: ['common'], //禁止访问的模块(多模块模式)
        default_module: 'home', //默认的模块
        deny_controller: [], //禁止访问的控制器
        default_controller: 'index', //默认控制器
        default_action: 'index', //默认方法
        prefix: [], // url prefix
        suffix: ['.jhtml'], // url suffix
        subdomain_offset: 2,
        subdomain: {}, //subdomain
    }
}
```

###自定义路由
除默认的单模块模式(controller/action)及多模块模式(module/controller/action）以外，还支持用户定制路由。
在项目中增加路由文件 config/router.js:
```
module.exports = {
    ['/product', {
        get: "/home/product/index"
    }],
    ['/product/:id', {
        get: "/home/product/detail",
        post: "/home/product/add",
        put: "/home/product/update",
        delete: "/home/product/delete",
    }],
    ['/product', "/home/product/index"]
}

```
按照实际项目需求进行修改即可。