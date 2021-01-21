#  AutoPermission
## **自动模拟点击开启手机权限，可以自由配置权限和操作步骤**

## **简介**
- 可自动开启各种敏感权限，如修改系统设置、悬浮窗等权限
- 引导开启无障碍功能
- 可用json文件配置权限、操作步骤、延迟时间等
- 可以适配多机型

## 理论上只要能正常开启无障碍的机型都是可以自动开启权限的
## 不同的机型可能需要适配不同的文案和按钮的ID，这个需要在json文件中自己定义，具体的方法可见下文。

## [更多信息点击这里观看](https://blog.csdn.net/ly502541243/article/details/108201569)

## **配置**

配置文件路径：***app/src/main/assets/step.json***

```json
{
    "delay_time": 600,//延时
    "type_id": 5,
    "describe": "显示在其他应用上面",
    "intent": {
      "uriData": "package&com.example.autopermission",
      "actionName": "android.settings.action.MANAGE_OVERLAY_PERMISSION"//需要打开的设置界面action
    },
    "step": [
      {
        "delay_time": 600,
        "find_text": "其他应用",
        "action_type": "ACTION_CLICK",//动作类型 此处为点击
        "click_type": "child",//点击类型为子布局
        "reality_node_name": "android.widget.TextView",//需要查找的节点名字
        "reality_node_id": ":id/checkbox&:id/switch_widget&switch"//需要查找的节点id 使用&符号可以匹配多种类型（不同手机可能id不同）
      },
      {
        "click_type": "system",
        "delay_time": 600,
        "action_type": "GLOBAL_ACTION_BACK"//返回按键
      }
    ]
  }
```
## **截图**

![](./picture1.gif)

![](./picture4.jpg)

![](./picture3.jpg)

![](./picture2.gif)


## **About me**
* [Email](LYYX@outlook.com)
* [WeiBo](http://weibo.com/liuyang6)
* [Blog](http://blog.csdn.net/ly502541243)
