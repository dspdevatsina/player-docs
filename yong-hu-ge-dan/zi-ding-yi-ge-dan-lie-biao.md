**查询自定义歌单列表**

接口： /user-album/list

方法： POST

示例： [https://api.ros.ai/player/user-album/list](https://api.ros.ai/player/user-album/list)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "parentId" : ""
}
```

其中参数意义如下

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | 设备TOKEN或者应用TOKEN |
| clientId | string | 必填 | 设备ID |
| userId | string | 可选 | 当歌单关联到设备上时，userId标识是哪个用户创建 |
| parentId | string | 可选 | 父歌单ID（暂不支持，不填）：当不填或者为空时，表示没有父歌单ID |

返回值

```
{
  "result" : 0,
  "msg" : "success",
  "data" : {
    "total" : 1,
    "list" : [
      {
        "albumId" : "1000",
        "parentId" : "100",
        "name" : "歌单标题",
        "templateId" : "",
        "total" : 10,
        "type":"album",
        "imgLarge" : "http://media.roobo.net/appimg/20161114_67fe4ba23ba80b325d4b388838d31853.png",
        "imgSmall" : "http://media.roobo.net/appimg/20161117_fea417c257b8b2826f801d41a3a48931.jpg"
      }
    ]
  }
}
```

其中返回值意义如下

| 参数 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.count | int | 用户歌单总数 |
| data.list\[\].id | int | 歌单ID |
| data.list\[\].type | string | 歌单类型： album-此歌单只包含资源；category-此歌单只包含子歌单 |
| data.list\[\].imgLarge | string | 歌单大图链接 |
| data.list\[\].imgSmall | string | 歌单小图链接 |
| data.list\[\].name | string | 歌单名称 |
| data.list\[\].total | int | 此歌单下包含的子歌单（或者资源）的总数量 |
| data.list\[\].templateId | string | 该歌单的模板歌单ID |



