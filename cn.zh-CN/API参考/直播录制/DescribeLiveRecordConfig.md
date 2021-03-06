# DescribeLiveRecordConfig {#reference3079 .reference}

查询域名下所有 App 录制配置。

## 请求参数 {#section_k4f_qm1_dfb .section}

|参数|类型|是否必选|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|DescribeLiveRecordConfig|系统规定参数。取值：DescribeLiveRecordConfig|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|AppName|String|否|testApp|直播流所属应用名称。|
|Order|String|否|asc|排序。

 -   asc：升序。
-   desc：降序。
-   默认值：asc

|
|PageNum|Integer|否|1| 分页的页码。

 默认值：1

 |
|PageSize|Integer|否|5| 每页大小。

 取值范围：5~30

 默认值：10

 |

## 返回参数 {#section_p4f_qm1_dfb .section}

|名称|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|5056369B-D337-499E-B8B7-B761BD37B08A|该条任务请求 ID。|
|LiveAppRecordList| | |录制配置。|
|  └DomainName|String|test.com|流所属加速域名。|
|  └AppName|String|test123|流所属应用名称。|
|  └OssEndpoint|String|oss-cn-shanghai.aliyuncs.com|OSS endpoint。|
|  └OssBucket|String|test123|OSS 存储 bucket 名称。|
|  └CreateTime|String|2016-05-20T09:33:38Z|创建时间。|
|  └RecordFormatList| | |格式列表。|
|    └Format|String|xxx|格式名称。|
|    └OssObjectPrefix|String|xxx|OSS 存储文件名。|
|    └SliceOssObjectPrefix|String|xxx|存储分片的 OSS 文件名。|
|    └CycleDuration|Integer|3600|周期录制时间。单位：秒。|
|PageNum|Integer|5|分页的页码。|
|PageSize|Integer|10|每页大小。|
|Order|String|desc|排序。|
|TotalPage|Integer|20|总页数。|
|TotalNum|Integer|12|符合条件的总个数。|

## 示例 {#section_zcx_4j1_dfb .section}

请求示例

```
https://live.aliyuncs.com/?Action=DescribeLiveRecordConfig&DomainName=xxxxx<公共请求参数> 
```

正常返回示例

JSON格式

```
{
    "LiveAppRecordList":{
        "LiveAppRecord":[{
            "AppName":"aliyuntest",
            "CreateTime":"2016-05-20T09:33:38Z",
            "DomainName":"xxxxx",
            "FormatList":{
                "Format":[{
                    "Name":"m3u8",
                    "OssObjectPrefix":"xxx",
                    "SliceOssObjectPrefix":"xxx"
                }]
            },
            "OssBucket":"chimang.bucket",
            "OssEndpoint":"oss-cn-hangzhou.aliyuncs.com"
        }]
    },
    "RequestId":"5056369B-D337-499E-B8B7-B761BD37B08A"
}
```

异常返回示例

JSON格式

```
{
    "Code":"InternalError",
    "HostId":"live.aliyuncs.com",
    "Message":"The request processing has failed due to some unknown error.",
    "RequestId":"6EBD1AC4-C34D-4AE1-963E-B688A228BE31"
}
```

## 错误码 { .section}

 [查看本产品错误码](https://error-center.aliyun.com/status/product/live) 

