**资源搜索**

对于ROOBO的海量资源，第三方可以使用该接口搜索资源或者专辑。

接口： /search

方法： POST

示例： [https://api.ros.ai/player/search](https://api.ros.ai/player/search)

请求参数：

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "ranges" : ["resource", "album"],
  "page" : 1,
  "count" : 20,
  "keywords" : ["刘德华"]
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必选 | 应用ID |
| token | string | 必选 | TOKEN |
| clientId | string | 可选 | 设备ID |
| userId | string | 可选 | 执行搜索操作的用户ID |
| keywords\[\] | string | 必选 | 搜索关键词 |
| ranges\[\] | string | 可选 | 搜索范围，搜索资源还是专辑；默认不填代表只搜索资源 |
| page | int | 可选 | 当前分页，默认是1 |
| count | int | 可选 | 结果数量，默认是20， 不能超过100 |

返回内容

```
{
    "result":0,
    "msg":"success",
    "data":{
        "resources":[
            {
                "resId":"aires:485965",
                "type":1,
                "name":"雨后",
                "favoriteId":"1000",
                "length":259,
                "content":"http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3",
                "artist":"歌手",
                "playUrls":{
                    "normal":{
                        "size":4072551,
                        "url":"http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3"
                    }
                },
                "album": {
                    "id": "11543",
                    "name": "古诗古词",
                    "imgLarge": "http://media.roo.bo//thirdparty/20170816/4acef775e7730c27ca3a92ca7167e7e6.png",
                    "imgSmall": "http://media.roo.bo//thirdparty/20170816/af47b76306a1f4813d8fc5f43680036c.png"
                }
            }
        ],
        "resourcesPager": {
            "page": 1,
            "pageSize": 20,
            "total": 1
        },
        "albums":[
            {
                "albumId":"9484",
                "favoriteId":"1000",
                "name":"不一样的卡梅拉",
                "description":"",
                "total":17,
                "imgThumb":"http://media.roobo.net/appimg/20161114_67fe4ba23ba80b325d4b388838d31853.png",
                "imgLarge":"http://media.roobo.net/appimg/20161117_fea417c257b8b2826f801d41a3a48931.jpg",
                "type":"album",
                "tags":[
                    "new"
                ]
            }
        ],
        "albumsPager": {
            "page": 1,
            "pageSize": 20,
            "total": 1
        }
    }
}
```

其中返回值

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.resources | array | [资源详情](/cms/mo-kuai-lie-biao.md) |
| data.albums | array | 参考：[歌单列表](/cms/ge-dan-lie-biao.md) |
| data.resourcesPager.page | int | 资源分页当前页数（从1开始） |
| data.resourcesPager.pageSize | int | 资源分页每页大小 |
| data.resourcesPager.total | int | 匹配资源总数量 |
| data.albumsPager.page | int | 歌单分页当前页数（从1开始） |
| data.albumsPager.pageSize | int | 歌单分页每页数量 |
| data.albumsPager.total | int | 匹配歌单总数量 |



