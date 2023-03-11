# 大凤林API

## 获取队伍信息

* 请求地址`https://cdn.r-mj.com/api/data.php`  
* 传入参数  
`t=tm_pw`  
`cid=队伍密码`  
* 例如【GET】
```
https://cdn.r-mj.com/api/data.php?t=tm_pw&cid=rjzfmh3lkt7khd4jeowk
```

### 响应
```json
{"tid":"8323","t_name":"\u4e03\u6708","t_player":"\u5b89\u4e01\ntouko\n\u897f\u98a8\u75e9\u99ac\n\u74dc\n\u4e03\u6708","t_sub":"","t_pw":"rjzfmh3lkt7khd4jeowk","t_join_time":"2022-10-19 12:11:05","t_join_ip":null,"t_type":"0","t_ps":"","cid":"143","qq":null,"ls_ip":null,"ls_time":"2022-11-10 20:07:00","img":""}
```
* `t_name`是队名  
* `t_player`是正选成员   
* `t_sub`是替补成员  
* `t_pw`是队伍密码
* `cid`是比赛编号
* `img`是队伍头像url


## 修改队伍信息
* 请求地址`https://cdn.r-mj.com/team_post.php`  
* 传入参数  
```
posttype: update
t_pw: rjzfmh3lkt7khd4jeowk
t_ps: 
cid: 143
linkurl: https://000.mk/img/none.jpg 
team_type: 0
postdata: 安丁
touko
西風痩馬
瓜
七月
```

其中【postdata】是多行文本。成员和替补合起来。用回车 \n 请求。 
* 例如【POST】https://cdn.r-mj.com/team_post.php
```
posttype=update&t_pw=rjzfmh3lkt7khd4jeowk&t_ps=&cid=143&postdata=%E5%AE%89%E4%B8%81%0Atouko%0A%E8%A5%BF%E9%A2%A8%E7%97%A9%E9%A6%AC%0A%E7%93%9C%0A%E4%B8%83%E6%9C%88%0A%0A&linkurl=https%3A%2F%2F000.mk%2Fimg%2Fnone.jpg+&team_type=0
```
### 响应
```json
{"msg":"\u63d0\u4ea4\u6210\u529f"}
```
中文提示是否错误之类的


## 获取比赛设置
* 请求地址`https://cdn.r-mj.com/api/data.php`  
* 传入参数【cid是比赛编号】
`t=admin`  
`cid=143`  
* 例如【GET】
```
https://cdn.r-mj.com/api/data.php?t=admin&cid=143
```

### 响应
```json
{"cid":"143","c_name":"台州花鸟风月雀庄团体赛","t_max":"40","t_type":"先鋒\\r\\n先鋒\\r\\n次鋒\\r\\n次鋒\\r\\n中堅\\r\\n中堅\\r\\n副將\\r\\n副將\\r\\n大將\\r\\n大將","c_gonggao":"台州雀魂团体赛","bm_st":"2022-08-27 12:00:00","bm_ed":"2022-08-21 12:00:00","r_type":"1","c_sub_t":"3","t_sub":"-1","c_round":"3","c_s_po":"25000","c_pad":"台州雀魂团体赛","c_banner":null,"STOP_EDIT":"0","ONLY_GET":"0","JOIN_END":"1","CS_END":"1"}
```

## 获取比赛所有队伍
* 请求地址`https://cdn.r-mj.com/api/data.php`  
* 传入参数【cid是比赛编号】
`t=team`  
`cid=143`  
* 例如【GET】
```
https://cdn.r-mj.com/api/data.php?t=team&cid=143
```

### 响应
```json
{"8323":{"tid":"8323","t_name":"七月","t_player":"安丁\\ntouko\\n西風痩馬\\n瓜\\n七月","t_sub":"","t_type":"0","img":"","t_ps":""},"8324":{"tid":"8324","t_name":"萤火","t_player":"念梦\\n草\\n嘲鸟\\n小郑\\n萤火","t_sub":"","t_type":"0","img":"","t_ps":""},"8325":{"tid":"8325","t_name":"猪猪","t_player":"秋秋\\nL3\\n小戊\\n辰胤\\n猪猪","t_sub":"","t_type":"0","img":"","t_ps":""},"8326":{"tid":"8326","t_name":"敌敌畏","t_player":"否急噶姆\\n西洲\\nshawn\\n百变小樱\\n敌敌畏","t_sub":"","t_type":"0","img":"","t_ps":""}}
```

## 获取比赛所有分组信息
* 请求地址`https://cdn.r-mj.com/api/data.php`  
* 传入参数【cid是比赛编号】
`t=class`  
`cid=143`  
* 例如【GET】
```
https://cdn.r-mj.com/api/data.php?t=class&cid=143
```

### 响应
```json
[{"rid":"14468","tid1":"8323","tid2":"8324","tid3":"8325","tid4":"8326","round":"4","t_class":"1","clsmark":"","code":"1"},{"rid":"13366","tid1":"8323","tid2":"8341","tid3":"8324","tid4":"8326","round":"3","t_class":"1","clsmark":"\u7b2c2\u5c4a\u51b3\u8d5b","code":"1"},{"rid":"13364","tid1":"8324","tid2":"8325","tid3":"8326","tid4":"8340","round":"2","t_class":"1","clsmark":"\u7b2c2\u5c4a\u7b2c1\u8f6e","code":"1"},{"rid":"13365","tid1":"8323","tid2":"8341","tid3":"8342","tid4":"8343","round":"2","t_class":"2","clsmark":"\u7b2c2\u5c4a\u7b2c1\u8f6e","code":"1"},{"rid":"13267","tid1":"8323","tid2":"8324","tid3":"8325","tid4":"8326","round":"1","t_class":"1","clsmark":"","code":"0"}]
```

## 添加分组信息
* 请求地址`https://cdn.r-mj.com/class-edit.php`  
* 传入参数
```
posttype: 4
cid: 143
c_pw: 123123
amark: 
acls: 1
2
acode: 1
1
atid1: 8323
8340
atid2: 8324
8341
atid3: 8325
8342
atid4: 8326
8343
atn1: 七月
百露
atn2: 萤火
哈吃
atn3: 猪猪
甲鱼
atn4: 敌敌畏
金华
rnd: 5
```

`acls`这些传入的都是多行文本，示例传入了2个小组。
这些多行文本都用回车(\r\n)隔开

* acls 第几组（从1开始）
* amark 组别的注释
* acode 天凤大会室地址/雀魂比赛场编号
* atid1 第一组的队伍编号（tid）
* atn1 第一个队伍的队名
* rnd 第几轮（第五轮=5）

## 抓取对战记录
* 请求地址`https://cdn.r-mj.com/edit_class_json.php` 
* 传入参数
```
type: login
cid: 143
rnd: 3
cls: 1
```
* cid =赛事编号
* rnd=轮次
* cls=组别
### 响应
```json
{"status":"2","data":[["\u661f\u661f","89700","-10300","L3","97300","-2700","\u5632\u9e1f","107500","7500","\u5426\u6025\u5676\u59c6","105500","5500","https:\/\/game.maj-soul.net\/1\/?paipu=221105-9b6cf0d5-c3e6-40db-a5c1-f946f9e437ff_a88442138"],["\u661f\u661f","95000","5300","L3","92600","-4700","\u5632\u9e1f","123200","15700","\u5426\u6025\u5676\u59c6","89200","-16300","https:\/\/game.maj-soul.net\/1\/?paipu=221105-e6aa57bb-f3cb-461e-bce4-938f1b6492e6_a88442138"],["\u74dc","94000","-1000","\u8ba9","92200","-400","\u6c34","120500","-2700","\u897f\u6d32","93300","4100","https:\/\/game.maj-soul.net\/1\/?paipu=221105-bd18d7df-5ebb-4924-a434-10f94aa6fb36_a88442138"],["\u74dc","91100","-2900","\u8ba9","89600","-2600","\u6c34","121500","1000","\u897f\u6d32","97800","4500","https:\/\/game.maj-soul.net\/1\/?paipu=221105-29a9d540-a5df-4de4-b6dd-7090ccadea5f_a88442138"],["\u5b89\u4e01","92800","1700","\u6469\u7f57","71300","-18300","\u5c01\u4e0d\u89c9","139600","18100","\u601d","96300","-1500","https:\/\/game.maj-soul.net\/1\/?paipu=221105-15026162-fd10-4180-812a-6cfbe8818d8b_a88442138"],["\u5b89\u4e01","87400","-5400","\u6469\u7f57","68100","-3200","\u5c01\u4e0d\u89c9","142100","2500","\u601d","102400","6100","https:\/\/game.maj-soul.net\/1\/?paipu=221105-975c055d-2403-45e3-817a-c197da4c2d2d_a88442138"],["touko","97000","9600","\u90a2\u4ed1","57900","-10200","\u5c0f\u90d1","121900","-20200","\u654c\u654c\u754f","123200","20800","https:\/\/game.maj-soul.net\/1\/?paipu=221106-47174557-8831-4fd7-a46d-9273bec99f03_a88442138"],["touko","86200","-10800","\u90a2\u4ed1","60900","3000","\u5c0f\u90d1","129700","7800","\u654c\u654c\u754f","123200","0","https:\/\/game.maj-soul.net\/1\/?paipu=221106-ebf24fb3-2659-4faa-9491-a6ef51c361c3_a88442138"],["\u897f\u98a8\u75e9\u99ac","114100","27900","\u54c8\u5403","46400","-14500","\u8424\u706b","129500","-200","\u5c0f\u6a31","110000","-13200","https:\/\/game.maj-soul.net\/1\/?paipu=221106-4f65da8b-4454-47dc-a927-62ea05e427b6_a88442138"],["\u897f\u98a8\u75e9\u99ac","120300","6200","\u54c8\u5403","76600","30200","\u8424\u706b","115900","-13600","\u5c0f\u6a31","87200","-22800","https:\/\/game.maj-soul.net\/1\/?paipu=221106-d5c0b70c-cc8d-4300-8916-4b9fd114ea5c_a88442138"]]}
```

## 添加对战记录
* 请求地址`https://cdn.r-mj.com/edit_class_json.php` 
* 传入参数
```
cid: 143
cls: 1
rnd: 3
type: update
name1[]: 星星
point1[]: 89700
score1[]: -10300
name2[]: L3
point2[]: 97300
score2[]: -2700
name3[]: 嘲鸟
point3[]: 107500
score3[]: 7500
name4[]: 否急噶姆
point4[]: 105500
score4[]: 5500
logurl[]: https://game.maj-soul.net/1/?paipu=221105-9b6cf0d5-c3e6-40db-a5c1-f946f9e437ff_a88442138
name1[]: 星星
point1[]: 95000
score1[]: 5300
name2[]: L3
point2[]: 92600
score2[]: -4700
name3[]: 嘲鸟
point3[]: 123200
score3[]: 15700
name4[]: 否急噶姆
point4[]: 89200
score4[]: -16300
logurl[]: https://game.maj-soul.net/1/?paipu=221105-e6aa57bb-f3cb-461e-bce4-938f1b6492e6_a88442138
name1[]: 瓜
point1[]: 94000
score1[]: -1000
name2[]: 让
point2[]: 92200
score2[]: -400
name3[]: 水
point3[]: 120500
score3[]: -2700
name4[]: 西洲
point4[]: 93300
score4[]: 4100
logurl[]: https://game.maj-soul.net/1/?paipu=221105-bd18d7df-5ebb-4924-a434-10f94aa6fb36_a88442138
name1[]: 瓜
point1[]: 91100
score1[]: -2900
name2[]: 让
point2[]: 89600
score2[]: -2600
name3[]: 水
point3[]: 121500
score3[]: 1000
name4[]: 西洲
point4[]: 97800
score4[]: 4500
logurl[]: https://game.maj-soul.net/1/?paipu=221105-29a9d540-a5df-4de4-b6dd-7090ccadea5f_a88442138
name1[]: 安丁
point1[]: 92800
score1[]: 1700
name2[]: 摩罗
point2[]: 71300
score2[]: -18300
name3[]: 封不觉
point3[]: 139600
score3[]: 18100
name4[]: 思
point4[]: 96300
score4[]: -1500
logurl[]: https://game.maj-soul.net/1/?paipu=221105-15026162-fd10-4180-812a-6cfbe8818d8b_a88442138
name1[]: 安丁
point1[]: 87400
score1[]: -5400
name2[]: 摩罗
point2[]: 68100
score2[]: -3200
name3[]: 封不觉
point3[]: 142100
score3[]: 2500
name4[]: 思
point4[]: 102400
score4[]: 6100
logurl[]: https://game.maj-soul.net/1/?paipu=221105-975c055d-2403-45e3-817a-c197da4c2d2d_a88442138
name1[]: touko
point1[]: 97000
score1[]: 9600
name2[]: 邢仑
point2[]: 57900
score2[]: -10200
name3[]: 小郑
point3[]: 121900
score3[]: -20200
name4[]: 敌敌畏
point4[]: 123200
score4[]: 20800
logurl[]: https://game.maj-soul.net/1/?paipu=221106-47174557-8831-4fd7-a46d-9273bec99f03_a88442138
name1[]: touko
point1[]: 86200
score1[]: -10800
name2[]: 邢仑
point2[]: 60900
score2[]: 3000
name3[]: 小郑
point3[]: 129700
score3[]: 7800
name4[]: 敌敌畏
point4[]: 123200
score4[]: 0
logurl[]: https://game.maj-soul.net/1/?paipu=221106-ebf24fb3-2659-4faa-9491-a6ef51c361c3_a88442138
name1[]: 西風痩馬
point1[]: 114100
score1[]: 27900
name2[]: 哈吃
point2[]: 46400
score2[]: -14500
name3[]: 萤火
point3[]: 129500
score3[]: -200
name4[]: 小樱
point4[]: 110000
score4[]: -13200
logurl[]: https://game.maj-soul.net/1/?paipu=221106-4f65da8b-4454-47dc-a927-62ea05e427b6_a88442138
name1[]: 西風痩馬
point1[]: 120300
score1[]: 6200
name2[]: 哈吃
point2[]: 76600
score2[]: 30200
name3[]: 萤火
point3[]: 115900
score3[]: -13600
name4[]: 小樱
point4[]: 87200
score4[]: -22800
logurl[]: https://game.maj-soul.net/1/?paipu=221106-d5c0b70c-cc8d-4300-8916-4b9fd114ea5c_a88442138
pw: 123123
```
其中
* pw: 赛事密码
* cid: 赛事编号
* cls: 组别
* rnd: 第几轮
* type: update
* name1[]: 选手1的昵称
* point1[]: 队伍1的队伍分数
* score1[]: 选手1的净得点
* name2[]: 选手2的昵称
* point2[]: 队伍2的队伍分数
* score2[]: 选手2的净得点
* name3[]: 选手3的昵称
* point3[]: 队伍3的队伍分数
* score3[]: 选手3的净得点
* name4[]: 选手4的昵称
* point4[]: 队伍4的队伍分数
* score4[]: 选手4的净得点
* logurl[]: 牌谱url

多个记录就多次添加