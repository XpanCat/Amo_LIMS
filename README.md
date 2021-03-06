# Amo_LIMS
Laboratory Information Management System for Amogene.

前期需求共分三个模块：
1. 管理员模块
- 管理员登录
- 管理员权限
- 管理员个人信息

2. 客户模块
- 客户信息档案
- 客户邮件发送
- 客户信息填写

3. 数据整理模块
- 数据上传
- 数据归档
- 数据检索


## 管理员模块
- 以OpenID登入，不设置注册系统；
- 设置管理员权限，用于创建项目号，修改项目内容；
- 管理员信息字段固定，数据表如下:

| Name  | property1 | property2 | property3 |
| ----  | --------- | --------- | --------- |
| char1 |           |           |           |
| char2 |           |           |           |
| char3 |           |           |           |
| char4 |           |           |           |
| char5 |           |           |           |

## 客户模块
- 邮件系统样式固定，主要发送"建库测序表"和"数据分析表"；
- 客户信息字段固定，数据表如下:

| Name  | property1 | property2 | property3 |
| ----  | --------- | --------- | --------- |
| char1 |           |           |           |
| char2 |           |           |           |
| char3 |           |           |           |
| char4 |           |           |           |
| char5 |           |           |           |

## 数据整理模块
- 外部用户填写：以管理员创建项目号后，生成唯一验证码，用于外部用户填写时的校验；

## 建库测序表

| 编号 | 表格名称      | 属性                                                         | 格式           | 含义                           | 备注                                                         |
| ---- | ------------- | ------------------------------------------------------------ | -------------- | ------------------------------ | ------------------------------------------------------------ |
| 1    | 项目编号      | 可以用数字、英文；不可以用中文；英文必须大写；符号只能使用横杠“-”； | AM20XX XXXX-XX | 公司前缀 + 年 + 月 + 日 + ？？ | 之前会有"9个、4个"之类的中文是否有意义                       |
| 2    | 客户          | 纯中文                                                       | 张三           |                                | 外国名字使用英文                                             |
| 3    | 爱默基因编号  | 可以用数字、英语；不能使用中文、符号；英文必须大写；         | SDC XXXX XXXX  | Sequencing DNA ChIP            |                                                              |
|      |               |                                                              | SDA XXXX XXXX  | Sequencing DNA   Amplicon      |                                                              |
|      |               |                                                              | 小基因组       | Sequencing DNA ???             | 不知道怎么定义                                               |
|      |               |                                                              | SRP XXXX XXXX  | Sequencing RNA PolyA           |                                                              |
|      |               |                                                              | SRR XXXX XXXX  | Sequencing RNA   Ribosome      | 有疑问，Ribosome测序类型可能与16s   18s等造成歧义            |
|      |               |                                                              | SRS XXXX XXXX  | Sequencing RNA sgRNA           |                                                              |
|      |               |                                                              | SRC XXXX XXXX  | Sequencing RNA   circleRNA     |                                                              |
| 4    | 建库类型      | 纯中文                                                       | 扩增子文库     |                                | 原表格中有"样品名称"与"建库类型"，信息描述类似，不知道是否可以去冗余，仅留下一个 |
| 5    | 测序类型      | 仅可以使用数字加英文；                                       | PE(SE)150      | 类型缩写+读长                  |                                                              |
| 6    | 样本类型      | 随意描述                                                     | 组织           |                                |                                                              |
| 7    | 物种类型      | 官方拉丁文                                                   | Homo_sapiens   | 属名_种加词                    | 使用二名法规范，见物种表；                                   |
| 8    | 测序量        | 仅可以使用数字加英文；                                       | 1G_rawdata     | 数值 rawdata(cleandata)        |                                                              |
| 9    | Index编号     | 仅可以使用数字加英文；                                       | A705           |                                | 既然有编号，序列属性业务能力范畴，是否可以不显示序列信息     |
| 10   | Index正向序列 | 仅可以使用英文                                               | ACCCAGCA       |                                |                                                              |
| 11   | RNA提取情况   | 仅从"无降解","轻微降解","严重降解"中选取                     |                |                                | 具体名词定义需要规范，这个我说不好。                         |
| 12   | 测序次数      | 仅从"首测","加测","重测","测试"中选取                        |                |                                | 具体名词定义需要规范，这个我说不好。                         |

## 数据分析表
