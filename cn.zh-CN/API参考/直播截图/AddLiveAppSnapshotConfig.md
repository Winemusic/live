# AddLiveAppSnapshotConfig {#reference2256 .reference}

针对直播流下的 AppName 配置截图信息，输出内容保存到 OSS 中，重新推流生效。

## 请求参数 {#section_k4f_qm1_dfb .section}

|参数|类型|是否必选|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|AddLiveAppSnapshotConfig|系统规定参数。取值：AddLiveAppSnapshotConfig|
|AppName|String|是|testApp| 直播流所属应用名称。

 支持通配符＊号，代表该域名下所有的 AppName。

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|OssBucket|String|是|test123|OSSBucket名称。|
|OssEndpoint|String|是|oss-cn-shanghai.aliyuncs.com|OSSEndpoint域名。|
|TimeInterval|Integer|是|5| 截图周期。

 取值范围：\[5，3600\]

 单位：秒。

 |
|OverwriteOssObject|String|否|\{AppName\}/\{StreamName\}.jpg| OSS 存储文件名，每次截图都覆盖此文件。

 -   小于 256bytes。
-   目前仅支持生成 jpg 图片。
-   支持变量匹配，包含 \{AppName\}、\{StreamName\}，如：\{AppName\}/\{StreamName\}.jpg。

 |
|SequenceOssObject|String|否|snapshot/\{AppName\}/\{StreamName\}/\{UnixTimestamp\}.jpg| OSS 存储文件名。每次截图都递增存储，DescribeLiveStreamSnapshotInfo接口查询一段时间的文件。

-   小于 256bytes。
-   目前仅支持生成 jpg 图片。
-   支持变量匹配，包含 \{AppName\}、\{StreamName\}、\{UnixTimestamp\}、\{Sequence\}，其中 \{UnixTimestamp\}、\{Sequence\} 必填一个，如：snapshot/\{AppName\}/\{StreamName\}/\{UnixTimestamp\}.jpg。

 |

## 返回参数 {#section_p4f_qm1_dfb .section}

|名称|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|该条任务请求 ID|

## 示例 {#section_zcx_4j1_dfb .section}

请求示例

```
 https://live.aliyuncs.com/?Action=AddLiveAppSnapshotConfig&DomainName=test101.aliyunlive.com&AppName=xxx&TimeInterval=10&OssEndpoint=endpoint&OssBucket=bucket&OverwriteOssObject=object&SequenceOssObject=object<公共请求参数>
```

**说明：** 关于公共请求参数详细内容，参见 [公共请求参数](cn.zh-CN/API参考/调用方式/公共参数.md#)。

正常返回示例

JSON格式

```
{
    "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
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

## 错误码 {#section_acp_wlc_dfb .section}

 [查看本产品错误码](https://error-center.aliyun.com/status/product/live) 

