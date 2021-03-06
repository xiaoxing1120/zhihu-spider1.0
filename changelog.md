# 更新历史

## 实验阶段

### 0.0.15

- [fix] 修复了当文章不属于任何专栏时，使用 ``article.column`` 获取时会出错的 Bug。

### 0.0.14

- [fix] 修复了知乎现在的 API 添加了新验证字段 UUID 和 UA 而导致的无法使用的 Bug。
- [change] 关闭非安全请求的警告和输入密码时的警告。

### 0.0.13

- [fix] 修复了保存答案或文章时文件名的扩展名部分会多一个点的 bug。
- [fix] 修复了保存答案或文章时传递进文件名没有进行非法字符过滤引发的 bug。

### 0.0.12 - 2016.05.29

- [add] 莫名其妙的好像知乎 API 限制了获取用户粉丝的数量，只允许获取前 5020 个？稍微加了个 Warning。

### 0.0.11 - 2016.05.15

- [fix] 我真是傻 QwQ，自动重试机制写错了，现在应该是对了……

### 0.0.10 - 2016.05.15

- [fix] 修复一个由于登录时服务器返回的数据和大多数情况不一致造成的无法登录的 Bug（Issue #13）
- [add] 为 `StreamingJSON` 类增加了 `raw_data` 方法，用于获取内部数据的副本

### 0.0.9 - 2016.05.15

- [change] 修改了 `ZhihuClient.login` 方法中某些失败信息，使其能更明确的说明失败原因
- [add] 尝试性的为网络请求加入了自动重试机制
- [add] 完善文档，加入了手机登录的说明

### 0.0.8 - 2016.05.04

- [fix] 修复了 `Topic.best_answerers` 因返回的 JSON 与常规返回不符造成的 Bug

### 0.0.7 - 2016.04.28

- [fix] 修复了设置代理后因为关闭了 SSL 而造成的报 Warning 的问题
- [add] `Comment` 类增加了获取父评论作者的 `reply_to` 属性

### 0.0.6 - 2016.04.21

- [fix] 修复了 `Collection` 类的 `answer_count` 属性无法使用的 bug
- [change] 由于发现知乎 API 无法获取除自己以外用户关注的收藏夹，将 `following_collections` 由 `People` 类 移动至 `Me` 类中

### 0.0.5 - 2016.04.18

- [add] `Topic` 类增加了 `followers` 属性，可获取话题关注者
- [add] `Me` 类增加了 `vote` 方法，可以给答案/文章/评论点赞同/[反对]/清除赞和反对。
- [add] `Me` 类增加了 `thanks` 方法，可以给答案点感谢/取消感谢
- [add] `Me` 类增加了 `unhelpful` 方法，可以给答案没有帮助/取消没有帮助
- [add] `Me` 类增加了 `follow` 方法，可以关注/取消关注问题/话题/用户/专栏/收藏夹
- [add] `Me` 类增加了 `block` 方法，可以屏蔽/取消屏蔽用户
- [add] `Me` 类增加了 `collect` 方法，可以将答案加入自己的收藏夹
- [add] `Me` 类增加了 `message` 方法，可以向别的用户发私信
- [add] `Me` 类增加了 `comment` 方法，可以向答案/文章/问题/收藏夹发送评论，并且支持回复特定评论
- [add] `Me` 类增加了 `delete` 方法，可以删除自己的答案/评论/收藏夹/文章

### 0.0.4 - 2016.04.16

- [change] 所有自定义异常修改为继承 `Exception` 类，遵循 Python 文档的要求。[REF](https://docs.python.org/2/library/exceptions.html#exceptions.Exception)
- [add] `ZhihuClient` 增加 `set_proxy` 方法，可设置代理
- [add] 增加了 `People` 类的 `activities` 属性，可以获取用户动态
- [fix] 修复 Python 2 下因为 `__init__.py` 文件中的 `__all__` 变量是 unicode 而造成的 `from xxx import *` 报错的 bug
- [change] 生成器不再尝试使用类内缓存的数据，而是一定会访问 API（改了一下实现，对用户接口没啥影响）
- [add] 小小的增加了一点没啥用的测试

### 0.0.3 - 2016.04.09

- [add] 增加了 `ZhihuClient.from_url` 方法，传入合法的知乎网址，就能生成对应的对象
- [add] 给 `BaseGenerator` 增加了 `add_params` 和 `set_params`  方法
- [fix] 修复了 `BaseGenerator` 在 Python 2 下有问题的情况。
- [fix] 修复了当用户的 `locations`，`educations`，`business`，`employments` 等属性值不存在强行获取会出错的 bug
- [add] 写完了文档
- [change] 改变了好多内部类名和变量名，不过对外部接口没有影响

### 0.0.2 - 2016.04.07

- [fix] 修复错误的 BASE_HTML_HEADER 值。原值会导致 html 文件在 Firefox 中打开时，由于没有编码信息显示而不正确的问题。
- [add] 完善文档，用户文档基本写完。

### 0.0.1 - 2016.04.07

首次发布，提供基础功能。
