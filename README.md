# WeChatApp
微信小程序笔记


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
