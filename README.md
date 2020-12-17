# 抖音爬虫最新方法，首页推荐视频列表、关注视频列表、同城视频列表、视频详情、用户粉丝列表



<a name="CrZyi"></a>
### 最近有需求需要爬取抖音的一些数据，网上的一些方法都比较老，由于抖音升级较快已经不太实用了，所以只能自己解决了。
本次是对最新版本抖音app（13.6.0版本）进行的数据的抓取。<br />主要是通过脱壳、frida的逆向开发，在java层和Native层请求参数逆向还原，以及ida动态调试so文件破解请求参数和加密算法实现的爬取。<br />目前已经能爬取到抖音的个人中心、首页推荐视频列表、关注视频列表、同城视频列表、视频详情、用户粉丝列表、用户关注列表、用户作品列表、用户喜欢列表、用户权限、抖音热榜、明星榜、直播榜、音乐榜等。
<a name="Vyw7X"></a>
### 一、个人中心数据（以明星万茜为例）
```
{
    "user":{
        "custom_verify":"演员万茜",
        "followers_detail":[
            {
                "name":"抖音",
                "icon":"http://p3.pstatp.com/origin/50ec00079b64de2050dc",
                "fans_count":3117098,
                "open_url":"snssdk1128://user/profile/2559257897875871?",
                "apple_id":"1142110895",
                "download_url":"https://d.douyin.com/JsvN/",
                "package_name":"com.ss.android.ugc.aweme",
                "app_name":"aweme"
            },
            {
                "fans_count":837857,
                "open_url":"snssdk143://profile?uid=54131370834",
                "apple_id":"529092160",
                "download_url":"https://d.toutiao.com/YjjY/",
                "package_name":"com.ss.android.article.news",
                "app_name":"news_article",
                "name":"头条",
                "icon":"http://p3.pstatp.com/origin/50ed00079a1b6b8d1fb1"
            },
            {
                "apple_id":"1086047750",
                "download_url":"http://d.huoshanzhibo.com/eFvB/",
                "package_name":"com.ss.android.ugc.live",
                "app_name":"live_stream",
                "name":"抖音火山版",
                "icon":"http://p3.pstatp.com/origin/2ea5c000abe106154adef",
                "fans_count":0,
                "open_url":"snssdk1112://profile?id=0"
            }
        ],
        "commerce_info":{
            "offline_info_list":[
 
            ],
            "challenge_list":[
 
            ],
            "task_list":null,
            "head_image_list":null,
            "smart_phone_list":null
        },
        "watch_status":false,
        "is_activity_user":false,
        "is_block":false,
        "with_commerce_entry":true,
        "profile_tab_type":0,
        "sec_uid":"MS4wLjABAAAA4_lIixBk6FAtLaq52ONCBDAqOd-qQtLAgMgGpjVEd0mLgZ8CM8nZA4TImrHTGnah",
        "enterprise_user_info":"{"commerce_info":{"offline_info_list":[],"challenge_list":[],"task_list":null,"head_image_list":null,"smart_phone_list":null},"homepage_bottom_toast":[],"permissions":[{"Id":4,"Key":"LiveShop","Name":"直播电商","AppId":1128,"Status":1,"Extra":null,"Customization":null,"Parent":0,"Actions":null},{"Id":5,"Key":"UserShop","Name":"个人橱窗","AppId":1128,"Status":1,"Extra":null,"Customization":null,"Parent":0,"Actions":null},{"Id":3,"Key":"ItemShop","Name":"视频电商","AppId":1128,"Status":1,"Extra":null,"Customization":null,"Parent":0,"Actions":null}]}",
        "follow_status":1,
        "sync_to_toutiao":1,
        "secret":0,
        "ins_id":"",
        "dongtai_count":28,
        "life_story_block":{
            "life_story_block":false
        },
        "tab_settings":{
            "private_tab":{
                "show_private_tab":false,
                "private_tab_style":1
            }
        },
        "message_chat_entry":true,
        "nickname":"万茜",
        "aweme_count":28,
        "school_name":"",
        "twitter_id":"",
        "with_fusion_shop_entry":true,
        "mplatform_followers_count":3954955,
        "country":"中国",
        "following_count":7,
        "room_id":0,
        "star_billboard_rank":16,
        "is_effect_artist":false,
        "is_star":true,
        "is_mix_user":false,
        "signature":"演员万茜",
        "show_favorite_list":true,
        "forward_count":0,
        "uid":"2559257897875871",
        "twitter_name":"",
        "follower_status":0,
        "district":"滨江",
        "video_cover":{
 
        },
        "original_musician":{
            "music_used_count":0,
            "digg_count":0,
            "music_count":0
        },
        "r_fans_group_info":{
 
        },
        "birthday_hide_level":1,
        "city":"杭州",
        "follower_count":3117098,
        "youtube_channel_title":"",
        "short_id":"0",
        "enterprise_verify_reason":"",
        "youtube_channel_id":"",
        "iso_country_code":"",
        "with_commerce_enterprise_tab_entry":false,
        "is_blocked":false,
        "display_wvalantine_activity_entry":true,
        "location":"杭州",
        "verification_type":1,
        "unique_id":"dyzd1sj2p8p3",
        "apple_account":0,
        }
    },
    "extra":{
        "now":1605952430000,
        "fatal_item_ids":[
 
        ],
        "logid":"2020112117535001020208903058B1B831"
    },
    "log_pb":{
        "impr_id":"2020112117535001020208903058B1B831"
    },
    "status_code":0
}
```
 
<a name="OdypO"></a>
### 二、关注列表
![image.png](https://cdn.nlark.com/yuque/0/2020/png/97322/1606784450273-64eb09e3-89dd-43fe-ab85-77b8d26dbc57.png#align=left&display=inline&height=499&margin=%5Bobject%20Object%5D&name=image.png&originHeight=998&originWidth=2858&size=1214293&status=done&style=none&width=1429)
<a name="5N08i"></a>
### 三、视频评论列表数据
![image.png](https://cdn.nlark.com/yuque/0/2020/png/97322/1606784468633-03da192b-423a-4735-8d7c-5ae78dd13502.png#align=left&display=inline&height=766&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1532&originWidth=1914&size=1256610&status=done&style=none&width=957)
<a name="Um9Tj"></a>
### 四、作品详情数据（数据较多，只列举了评论、点赞、播放数量等部分数据）
![](https://cdn.nlark.com/yuque/0/2020/png/97322/1606784405018-6b4b445e-cd12-4dba-b95b-e167a40bc352.png#align=left&display=inline&height=52&margin=%5Bobject%20Object%5D&originHeight=92&originWidth=1842&size=0&status=done&style=none&width=1051)<br />其他数据就不依次列举了。<br />
<br />——————————————————————————————————————————————
<a name="9794cc28"></a>
#### TiToData：专业的短视频、直播数据接口服务平台。
<a name="1c5f89ff"></a>
#### 更多信息请联系： [TiToData](https://www.titodata.com?from=douyinarticle)
覆盖主流平台：抖音，快手，小红书，TikTok，YouTube
