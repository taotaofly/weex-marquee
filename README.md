# weex-marquee
weex custom component---marquee,can Infinite scrolling.可以无限滚动.

**注意:**这个组件不一定使用了任何地方,而且你可能需要对于你自己的业务进行专门定制和更改组件内部代码,如果你发现组件有任何问题,请提交一个issues.

## 安装

下载本库然后引用组件:

```javascript
require("./components/marquee.we");
```

## 使用

```html
<template>
	<scroller class="wrapper">
		<marquee marqueelist="{{marqueeList}}" timefn="ease-out" duration="{{duration}}" fontheight="50" fontsize="40" interval="{{interval}}" class="marquee"></marquee>
		<text>一个有十个数据,0~9</text>
	</scroller>
</template>

<style>
.wrapper { 
	width: 750; 
	position: absolute; 
	top: 0; 
	left: 0; 
	right: 0; 
	bottom: 0;
	align-items: center; 
	justify-content: center;
}
</style>

<script>
require("./components/marquee.we");
module.exports = {
	data: {
		marqueeList:[
			0,1,2,3,4,5,6,7,8,9
		],
		interval:2000,
		duration:500
	}
}
</script>
```

引用组件后就可以直接在你的we文件内这样使用:

```html
<marquee marqueelist="{{marqueeList}}" timefn="ease-out" duration="{{duration}}" fontheight="50" fontsize="40" interval="{{interval}}"></marquee>
```

当然组件有很多属性需要你去配置,各个属性解释:

1. `marqueelist`:这是你的数据.
2. `timefn`:动画函数,包括"ease","ease-in","ease-out","liner"等等,默认为"ease-out".
3. `duration`:单次动画持续时间.默认500毫秒
4. `fontheight`:字体高度.默认40
5. `fontsize`:字体大小.默认30
6. `interval`:每个动画间隔时间.默认2000毫秒

## 扩展

因为时间有限,并不能考虑所有的使用问题,所以如果你有能力可以自己动手扩展一下,完成后如果觉得不错可以贡献一下你的代码.

## 为什么造轮子

有些人和我一样,对官方的那个`wxc-marquee`组件不太满意,比如无法实现无限滚动的效果,因此只能自己取实现,所以我花了一个上午的时间来构建了这个组件.