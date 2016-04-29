boli-cli
========

基于webpack的前端工程构建工具

boli is short for bolshoi

### 安装

```
npm install boli-cli -g
```

### 编译项目文件

1.	在项目根目录下创建文件`boli-conf.js`;
2.	编辑`boli-conf.js`中的配置项，比如js文件的编译配置如下：

	```
	// 同名配置覆盖父级
	boli.config.spec('js', {
	    // 源文件扩展名
	    extType: 'js',
	    // 源文件使用的编码类型，值可以是单个string，也可以是数组
	    srcType: ['es2015', 'react'],
	    // js文件目录，默认为js
	    dirname: 'js',
	    // 是够uglify
	    uglify: true,
	    // 是否compress
	    compress: true,
	    // 是否使用hash指纹
	    useHash: true,
	    // 部署配置项，同名配置会覆盖上层配置
	    deploy: {
	        server: '192.168.1.1',
	        path: '/suyun/static/js'
	    }
	});
	```

	在项目根目录下执行`boli build`

### 使用插件

编辑`boli-conf.js`，使用API `boli.use`引入插件，比如：

```
boli.use('boli-plugin-loader-vue');
```

boli会判断用户是否已安装此插件，如果没有，则boli会自动安装此插件。
