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
        deny_modules: ['common'], //禁止访问的模块
        default_module: 'home', //默认的模块
        default_controller: 'index', //默认控制器
        default_action: 'index', //默认方法
        prefix: [], // url prefix
        suffix: ['.jhtml'], // url suffix
        subdomain_offset: 2,
        subdomain: {}, //subdomain
    }
}
```