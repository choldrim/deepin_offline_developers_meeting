因为这个项目的分享是当场演示，没有ppt，所以就直接上传一些截图吧
![reviews](https://raw.githubusercontent.com/choldrim/deepin_offline_developers_meeting/master/images/reviews.png)
![details.png](https://raw.githubusercontent.com/choldrim/deepin_offline_developers_meeting/master/images/details.png)
![client.png](https://raw.githubusercontent.com/choldrim/deepin_offline_developers_meeting/master/images/client.png)
![client_submit_report.png](https://github.com/choldrim/deepin_offline_developers_meeting/images/)
![client_submit_report.png](https://raw.githubusercontent.com/choldrim/deepin_offline_developers_meeting/master/images/client_submit_report.png)
![create_new.png](https://raw.githubusercontent.com/choldrim/deepin_offline_developers_meeting/master/images/create_new.png)

### 名词说明：
#### **base仓库：**将要合并进入的基础仓库，如：deepin仓库
#### **rpa/ppa仓库：**提交合并请求的个人仓库，如：dstore仓库
  - (rpa是指：Review Package Archives, ppa是指：Personal Package Archives)

### 简单说明：
- 我们设想是把一次仓库的合并请求类比成代码的一次review

- review由ppa维护者直接提交，提交后可以自动生成仓库相对与base仓库的变更，包括version变更和详细的changlog（changlog在实现中）

- review提交后测试者可以使用客户端（图：client）初始化测试源和提交测试报告

- review系统的提交测试报告接口是开放的，因此，可以由其他测试工具（如jenkins、openqa等）提交自动化测试报告

- 完成测试阶段后，由仓库管理人员进行仓库合并，合并成功后，review的生命周期完成


#### 由于仓库合并和和git仓库存在一定差异性，**可能**会出现的缺陷，如:
- 回归测试发现了问题不能直接如git revert直接回退
- 提交了ppa review后，不能再对ppa进行修改，否则有可能导致ppa测试时和提交时信息不一致
...  
这些缺陷应该都是有对应的解决方案，但不是近期/短期要解决的问题
