# vue-picker-calendar

##vue 日历选择控件
主要应用于移动端.PC端也可使用
```

日历选择，可通过tipsData属性绑定日历事件，进去当前事件日期会高亮显示，点击该日期可回传日历信息，可通过 setCalendar函数获取当前日历信息
点击年月日可调出，仿ios的picker模式选择年月日（引用了better-picker插件（https://www.npmjs.com/package/better-picker））
### github 地址：  https://github.com/mangohouse/vue-picker-calendar
###使用方法如下
```js
    npm install  vue-picker-calendar --save-dev
```
```html
<template>
    <div>
        <vue-calendar :originDateValue="originSetDateValue" :tipsData="tipsData" @set-Calendar="setCalendar" :startYear="startYear" :endYear="endYear"></vue-calendar>
        <!-->设置 @set-Calendar="setCalendar" 才能获取日期及日历回调函数
             会返回以下数据 {
                    day: i,
                    month: String(+this.currentMonth + 1),
                    date: itemDate1,
                    tipsData: null
                }
        </-->
    </div>
    </div>
</template>
```
```js
<script>

    import vueCalendar from 'vue-picker-calendar'
    import Css from 'vue-picker-calendar/dist/vue-calendar.min.css'
    export default {
        name: 'vueCalendar',
        data() {
            return {
                today: 0,
                originSetDateValue: '2017-11-8', //设置初始日期,默认当前日期
                startYear:1990, //起始年份
                endYear:2020,//结束年份
                tipsData: { //传入的日历数据，必须以日期为键值格式为2008-8-8
                    '2017-7-6': [{
                        contest: 'hellohello'
                    }, {
                        'task': ['100', '200']
                    }],
                    '2017-7-5': [{
                        contest: 'pk'
                    }, {
                        'task': ['100', '200']
                    }],
                    '2017-7-9': [{
                        contest: 'nba'
                    }, {
                        'task': ['100', '200']
                    }],
                    '2017-8-5': [{
                        contest: 'hello world'
                    }, {
                        'task': ['100', '200']
                    }],
                     '2017-9-5': [{
                        contest: 'hello world'
                    }, {
                        'task': ['100', '200']
                    }]

                }
            }
        },
        methods: {
            setCalendar(args) { //通过该函数可获取当前日期的日历事件
                console.log(args)
            }
        },
        components: {
            vueCalendar
        },
        created() {
            // this.init()
        },
        updated() {

        },
        mounted() {

        }
    }
</script>
```
