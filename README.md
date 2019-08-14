# demo-scroll

## 功能
实现VUE列表点击进入详情后，再返回保留先前列表的滚动位置。

**主要思路是**
1. 在点击事件中记录当前滚动位置
2. 返回后待列表数据渲染完成后，恢复至该位置
3. 由于是单页程序，切换路由并不会导致state列表中的数据消失，所以返回时可以直接使用该数据。初次时入页面
   时，可根据列表长度为0去远程加载。
4. vue router 本身的scrollBehavor只针对hash模式有效，并且单一页面容器，不够灵活。

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
