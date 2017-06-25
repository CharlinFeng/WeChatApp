# WeChatApp
微信小程序笔记


<br/>

#### 全新安装，请设置修改文件自动保存！否则新建删除文件会出现各种问题。

<br/><br/>

·参数定义
===========

#### 1.在APP里面自定义全局属性：


        //app.js
        App({

          p: { //p名字可以随便叫
            userModel: null
          }
        })
        
使用的时候是： getApp().p.userModel


<br>
####2.在Controller里面定义属性：

        var app = getApp(); //获取全局app

        Page({
          data: {
            um: null,
            pwd: null
          }
        })


<br/>

·弹性布局
===========

    display: flex; height: 500rpx; flex-direction: column; justify-content: space-around;
    
参考页面：http://www.jianshu.com/p/f82262002f8a


<br/>

·事件
===========

        //wxml代码：
        <view class="item" bindtap="clickItems" data-id="item1">item1</view>
        <view class="item" bindtap="clickItems" data-id="item2">item2</view>
    
        //js代码
        var param = {

          data: {
            defaultText: "请点击"
          },

          clickItems: function(e){

            var id = e.currentTarget.dataset.id;
            param.data.defaultText = "您点击了视图";
            //刷新数据
            this.setData(param.data);
          }
        };

        Page(param);





<br/>

·Block循环
===========
        <view>

          <block wx:for = "{{icons}}">

            <icon type="{{item}}" size = "40" />

          </block>

        </view>
        
<br/>

·tabBar
===========
在app.json里面直接配置，敲击tabbar即可。同时最好删除默认的index和log页面。新建页面建议小写。
官方文档：https://mp.weixin.qq.com/debug/wxadoc/dev/framework/config.html

<br/>

·App
===========
可以通过App()获取到app实例，并可以直接定义并读取数据，调用app内部定义的方法。
