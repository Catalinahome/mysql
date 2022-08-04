
## /信息查询接口
```text
暂无描述
```
#### 接口状态
> 开发中

#### 接口URL
> 未填写

#### 请求方式
> POST

#### Content-Type
> json

#### 请求Body参数
```javascript
{
	"RequestId": "111",
	"RequestTime": "2022-08-01 01:02:03",
	"BatchQuery": "0",
	"TopK":"10",
	"PharmacyData":[
		{"TradeName": "风寒感冒宁颗粒",
	     "ManufacturerName": "云南白药集团股份有限公司",
		"CommonName": "风寒感冒宁颗粒",
		"Specification": "每袋装8g(含乳糖)",
		"DosageForm": "颗粒剂",
		"Package": "每袋装8g(含乳糖)",
		"CommodityId": "C100",
		"ApprovalNumber": "国药准字Z112233"},
		{"TradeName": "风寒感冒宁颗粒",
		"ManufacturerName": "云南白药集团股份有限公司",
		"CommonName": "风寒感冒宁颗粒",
		"Specification": "每袋装8g(含乳糖)",
		"DosageForm": "颗粒剂",
		"Package": "每袋装8g(含乳糖)",
		"CommodityId": "C100",
		"ApprovalNumber": "国药准字Z112233"}]
}
```
参数名 | 示例值 | 参数类型 | 是否必填 | 参数描述
--- | --- | --- | --- | ---
RequestId | 111 | String | 是 | 请求消息的唯一标识，由接口客户端生成，使用 UUID
RequestTime | 2022-08-01 01:02:03 | String | 是 | 请求时间， 格式：2022-08-01 01:02:03
BatchQuery | 0 | int | 是 | 是否批量查询，是：1；否：0
TopK | 10 | int | 是 | 期望的药品匹配数量
PharmacyData | [ 		{"TradeName": "风寒感冒宁颗粒", 	     "ManufacturerName": "云南白药集团股份有限公司", 		"CommonName": "风寒感冒宁颗粒", 		"Specification": "每袋装8g(含乳糖)", 		"DosageForm": "颗粒剂", 		"Package": "每袋装8g(含乳糖)", 		"CommodityId": "C100", 		"ApprovalNumber": "国药准字Z112233"}, 		{"TradeName": "风寒感冒宁颗粒", 		"ManufacturerName": "云南白药集团股份有限公司", 		"CommonName": "风寒感冒宁颗粒", 		"Specification": "每袋装8g(含乳糖)", 		"DosageForm": "颗粒剂", 		"Package": "每袋装8g(含乳糖)", 		"CommodityId": "C100", 		"ApprovalNumber": "国药准字Z112233"}] | list | 是 | 药店数据
PharmacyData.TradeName | 风寒感冒宁颗粒 | String | 是 | 商品名
PharmacyData.ManufacturerName | 云南白药集团股份有限公司 | String | 是 | 厂商名
PharmacyData.CommonName | 风寒感冒宁颗粒 | String | 是 | 通用名
PharmacyData.Specification | 每袋装8g(含乳糖) | String | 是 | 规格
PharmacyData.DosageForm | 颗粒剂 | String | 是 | 剂型
PharmacyData.Package | 每袋装8g(含乳糖) | String | 是 | 包装
PharmacyData.CommodityId | C100 | String | 是 | 商品ID
PharmacyData.ApprovalNumber | 国药准字Z112233 | String | 是 | 批准文号
#### 预执行脚本
```javascript
暂无预执行脚本
```
#### 后执行脚本
```javascript
暂无后执行脚本
```
#### 成功响应示例
```javascript
{
    "ResponseId": "111",
    "ResponseTime": "2022-08-01 01:02:03",
    "MappingRes": [[
        {
        "TradeName": "风寒感冒宁颗粒",
        "ManufacturerName": "云南白药集团股份有限公司",
        "CommonName": "风寒感冒宁颗粒",
        "Specification": "每袋装8g(含乳糖)",
        "DosageForm": "颗粒剂",
        "Package": "每袋装8g(含乳糖)",
        "ApprovalNumber":"国药准字Z112233",
        "MappingRelationship":{"S101":"C100"}
        },
        {
        "TradeName": "风寒感冒宁颗粒",
        "ManufacturerName": "云南白药集团股份有限公司",
        "CommonName": "风寒感冒宁颗粒",
        "Specification": "每袋装6g",
        "DosageForm": "颗粒剂",
        "Package": "每袋装6g",
        "ApprovalNumber":"国药准字Z112245",
        "MappingRelationship":{"S100":"C100"}
        }
    ]]
}
```
参数名 | 示例值 | 参数类型 | 参数描述
--- | --- | --- | ---
ResponseId | 111 | String | 响应ID,响应的唯一标识，由接口服务端生成，使用 UUID
ResponseTime | 2022-08-01 01:02:03 | String | 服务端返回响应时间， 格式：2015-01-01 01:02:03
MappingRes | [[         {         "TradeName": "风寒感冒宁颗粒",         "ManufacturerName": "云南白药集团股份有限公司",         "CommonName": "风寒感冒宁颗粒",         "Specification": "每袋装8g(含乳糖)",         "DosageForm": "颗粒剂",         "Package": "每袋装8g(含乳糖)",         "ApprovalNumber":"国药准字Z112233",         "MappingRelationship":{"S101":"C100"}         },         {         "TradeName": "风寒感冒宁颗粒",         "ManufacturerName": "云南白药集团股份有限公司",         "CommonName": "风寒感冒宁颗粒",         "Specification": "每袋装6g",         "DosageForm": "颗粒剂",         "Package": "每袋装6g",         "ApprovalNumber":"国药准字Z112245",         "MappingRelationship":{"S100":"C100"}         }     ]] | list | 映射结果列表
MappingRes.0.TradeName | 风寒感冒宁颗粒 | String | 商品名
MappingRes.0.ManufacturerName | 云南白药集团股份有限公司 | String | 厂商名
MappingRes.0.CommonName | 风寒感冒宁颗粒 | String | 通用名
MappingRes.0.Specification | 每袋装8g(含乳糖) | String | 规格
MappingRes.0.DosageForm | 颗粒剂 | String | 剂型
MappingRes.0.Package | 每袋装8g(含乳糖) | String | 包装
MappingRes.0.ApprovalNumber | 国药准字Z112233 | String | 批准文号
MappingRes.0.MappingRelationship | {"S100":"C100"} | dict | 映射关系
## /入库状态接口
```text
暂无描述
```
#### 接口状态
> 开发中

#### 接口URL
> 未填写

#### 请求方式
> POST

#### Content-Type
> json

#### 请求Body参数
```javascript
{
	"RequestId": "111",
	"RequestTime": "2022-08-01 01:02:03",
	"CommodityId": "C100",
	"StandardId": "S100",
	"SubLibraryId": "SL100",
	"Type":"0"
}
```
参数名 | 示例值 | 参数类型 | 是否必填 | 参数描述
--- | --- | --- | --- | ---
RequestId | 111 | String | 是 | 请求消息的唯一标识，由接口客户端生成，使用 UUID
RequestTime | 2022-08-01 01:02:03 | String | 是 | 请求时间， 格式：2022-08-01 01:02:03
CommodityId | C100 | String | 是 | 商品ID
StandardId | S100 | String | 是 | 标准ID
SubLibraryId | SL100 | String | 是 | 子库ID
Type | 0 | int | 是 | 入库状态，通过：1；驳回：0
#### 预执行脚本
```javascript
暂无预执行脚本
```
#### 后执行脚本
```javascript
暂无后执行脚本
```
#### 成功响应示例
```javascript
{
	"ResponseId": "111",
	"ResponseTime": "2022-08-01 01:02:03",
	"ResponseCode": "success"
}
```
参数名 | 示例值 | 参数类型 | 参数描述
--- | --- | --- | ---
ResponseId | 111 | String | 响应ID,响应的唯一标识，由接口服务端生成，使用 UUID
ResponseTime | 2022-08-01 01:02:03 | String | 服务端返回响应时间， 格式：2015-01-01 01:02:03
ResponseCode | success | String | 响应编码，"success":成功；"fail":"失败"
## /问题反馈接口（暂不实现）
```text
暂无描述
```
#### 接口状态
> 开发中

#### 接口URL
> 未填写

#### 请求方式
> POST

#### Content-Type
> json

#### 请求Body参数
```javascript
{
	"RequestId": "111",
	"RequestTime": "2022-08-01 01:02:03",
	"CommodityId": "C100",
	"MappingRelationship": "[{\"S100\":\"C100\"},{\"S101\":\"C100\"}]"
}
```
参数名 | 示例值 | 参数类型 | 是否必填 | 参数描述
--- | --- | --- | --- | ---
RequestId | 111 | String | 是 | 请求消息的唯一标识，由接口客户端生成，使用 UUID
RequestTime | 2022-08-01 01:02:03 | String | 是 | 请求时间， 格式：2022-08-01 01:02:03
CommodityId | C100 | String | 是 | 商品ID
MappingRelationship | [{"S100":"C100"},{"S101":"C100"}] | list | 是 | 映射关系
#### 预执行脚本
```javascript
暂无预执行脚本
```
#### 后执行脚本
```javascript
暂无后执行脚本
```
#### 成功响应示例
```javascript
{
	"ResponseId": "111",
	"ResponseTime": "2022-08-01 01:02:03",
	"ResponseCode": "success"
}
```
参数名 | 示例值 | 参数类型 | 参数描述
--- | --- | --- | ---
ResponseId | 111 | String | 响应ID,响应的唯一标识，由接口服务端生成，使用 UUID
ResponseTime | 2022-08-01 01:02:03 | String | 服务端返回响应时间， 格式：2015-01-01 01:02:03
ResponseCode | success | String | 响应编码，"success":成功；"fail":"失败"
## /更新同步接口
```text
暂无描述
```
#### 接口状态
> 开发中

#### 接口URL
> 未填写

#### 请求方式
> POST

#### Content-Type
> json

#### 请求Body参数
```javascript
{
	"RequestId": "111",
	"RequestTime": "2022-08-01 01:02:03",
	"StandardId": "S100",
	"SubLibraryId": "SL100",
	"CommodityId": "C100",
	"ModiType": "delete",
	"DataBeforeChange": "{\n\t\"TradeName\": \"风寒感冒宁颗粒\",\n\t\"ManufacturerName\": \"云南白药集团股份有限公司\",\n\t\"CommonName\": \"风寒感冒宁颗粒\",\n\t\"Specification\": \"每袋装8g(含乳糖)\",\n\t\"DosageForm\": \"颗粒剂\",\n\t\"Package\": \"每袋装8g(含乳糖)\",\n\t\"CommodityId\": \"C100\",\n\t\"ApprovalNumber\": \"国药准字Z112233\"\n}",
	"DataAfterChange": "{\n\t\"TradeName\": \"风寒感冒宁颗粒\",\n\t\"ManufacturerName\": \"云南白药集团股份有限公司\",\n\t\"CommonName\": \"风寒感冒宁颗粒\",\n\t\"Specification\": \"每袋装8g\",\n\t\"DosageForm\": \"颗粒剂\",\n\t\"Package\": \"每袋装8g\",\n\t\"CommodityId\": \"C100\",\n\t\"ApprovalNumber\": \"国药准字Z112233\"\n}"
}
```
参数名 | 示例值 | 参数类型 | 是否必填 | 参数描述
--- | --- | --- | --- | ---
RequestId | 111 | String | 是 | 请求消息的唯一标识，由接口客户端生成，使用 UUID
RequestTime | 2022-08-01 01:02:03 | String | 是 | 请求时间， 格式：2022-08-01 01:02:03
StandardId | S100 | String | 是 | 标准ID
SubLibraryId | SL100 | String | 是 | 子库ID
CommodityId | C100 | String | 是 | 商品ID
ModiType | delete | String | 是 | 更新类型，删除id:delete;内容变更:update
DataBeforeChange | {	"TradeName": "风寒感冒宁颗粒",	"ManufacturerName": "云南白药集团股份有限公司",	"CommonName": "风寒感冒宁颗粒",	"Specification": "每袋装8g(含乳糖)",	"DosageForm": "颗粒剂",	"Package": "每袋装8g(含乳糖)",	"CommodityId": "C100",	"ApprovalNumber": "国药准字Z112233"} | dict | 是 | 变更前数据
DataAfterChange | {	"TradeName": "风寒感冒宁颗粒",	"ManufacturerName": "云南白药集团股份有限公司",	"CommonName": "风寒感冒宁颗粒",	"Specification": "每袋装8g",	"DosageForm": "颗粒剂",	"Package": "每袋装8g",	"CommodityId": "C100",	"ApprovalNumber": "国药准字Z112233"} | dict | 是 | 变更后数据
#### 预执行脚本
```javascript
暂无预执行脚本
```
#### 后执行脚本
```javascript
暂无后执行脚本
```
#### 成功响应示例
```javascript
{
	"ResponseId": "111",
	"ResponseTime": "2022-08-01 01:02:03",
	"ResponseCode": "success"
}
```
参数名 | 示例值 | 参数类型 | 参数描述
--- | --- | --- | ---
ResponseId | 111 | String | 响应ID,响应的唯一标识，由接口服务端生成，使用 UUID
ResponseTime | 2022-08-01 01:02:03 | String | 服务端返回响应时间， 格式：2015-01-01 01:02:03
ResponseCode | success | String | 响应编码，"success":成功；"fail":"失败"
## /编辑通知接口
```text
暂无描述
```
#### 接口状态
> 开发中

#### 接口URL
> 未填写

#### 请求方式
> POST

#### Content-Type
> json

#### 请求Body参数
```javascript
{
	"RequestId": "111",
	"RequestTime": "2022-08-01 01:02:03",
	"StandardId": "S100",
	"SubLibraryId": "SL100",
	"CommodityId": "C100",
	"ModiType": "delete",
	"DataBeforeChange": "{\n\t\"TradeName\": \"风寒感冒宁颗粒\",\n\t\"ManufacturerName\": \"云南白药集团股份有限公司\",\n\t\"CommonName\": \"风寒感冒宁颗粒\",\n\t\"Specification\": \"每袋装8g(含乳糖)\",\n\t\"DosageForm\": \"颗粒剂\",\n\t\"Package\": \"每袋装8g(含乳糖)\",\n\t\"CommodityId\": \"C100\",\n\t\"ApprovalNumber\": \"国药准字Z112233\"\n}",
	"DataAfterChange": "{\n\t\"TradeName\": \"风寒感冒宁颗粒\",\n\t\"ManufacturerName\": \"云南白药集团股份有限公司\",\n\t\"CommonName\": \"风寒感冒宁颗粒\",\n\t\"Specification\": \"每袋装8g\",\n\t\"DosageForm\": \"颗粒剂\",\n\t\"Package\": \"每袋装8g\",\n\t\"CommodityId\": \"C100\",\n\t\"ApprovalNumber\": \"国药准字Z112233\"\n}"
}
```
参数名 | 示例值 | 参数类型 | 是否必填 | 参数描述
--- | --- | --- | --- | ---
RequestId | 111 | String | 是 | 请求消息的唯一标识，由接口客户端生成，使用 UUID
RequestTime | 2022-08-01 01:02:03 | String | 是 | 请求时间， 格式：2022-08-01 01:02:03
StandardId | S100 | String | 是 | 标准ID
SubLibraryId | SL100 | String | 是 | 子库ID
CommodityId | C100 | String | 是 | 商品ID
ModiType | delete | String | 是 | 更新类型，删除id:delete;内容变更:update
DataBeforeChange | {	"TradeName": "风寒感冒宁颗粒",	"ManufacturerName": "云南白药集团股份有限公司",	"CommonName": "风寒感冒宁颗粒",	"Specification": "每袋装8g(含乳糖)",	"DosageForm": "颗粒剂",	"Package": "每袋装8g(含乳糖)",	"CommodityId": "C100",	"ApprovalNumber": "国药准字Z112233"} | dict | 是 | 变更前数据
DataAfterChange | {	"TradeName": "风寒感冒宁颗粒",	"ManufacturerName": "云南白药集团股份有限公司",	"CommonName": "风寒感冒宁颗粒",	"Specification": "每袋装8g",	"DosageForm": "颗粒剂",	"Package": "每袋装8g",	"CommodityId": "C100",	"ApprovalNumber": "国药准字Z112233"} | dict | 是 | 变更后数据
#### 预执行脚本
```javascript
暂无预执行脚本
```
#### 后执行脚本
```javascript
暂无后执行脚本
```
#### 成功响应示例
```javascript
{
	"ResponseId": "111",
	"ResponseTime": "2022-08-01 01:02:03",
	"ResponseCode": "success"
}
```
参数名 | 示例值 | 参数类型 | 参数描述
--- | --- | --- | ---
ResponseId | 111 | String | 响应ID,响应的唯一标识，由接口服务端生成，使用 UUID
ResponseTime | 2022-08-01 01:02:03 | String | 服务端返回响应时间， 格式：2015-01-01 01:02:03
ResponseCode | success | String | 响应编码，"success":成功；"fail":"失败"
