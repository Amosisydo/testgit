```mermaid
useCaseDiagram
    actor 普通用户 as U
    actor 管理员 as A
    actor 系统 as S

    rectangle 系统边界 {
        (用户注册登录) as UC1
        (博客发布与管理) as UC2
        (博客展示) as UC3
        (评论互动) as UC4
        (用户中心) as UC5
        (热门推荐) as UC6
        (后台管理) as UC7
        
        U --> UC1 : 注册/登录
        U --> UC2 : 发布文章
        U --> UC3 : 浏览/搜索
        U --> UC4 : 评论/点赞
        U --> UC5 : 维护资料
        
        A --> UC7 : 执行管理
        S --> UC6 : 生成推荐
        S --> UC3 : 计算热度
        
        UC1 ..> UC7 : <<extend>>
        UC3 ..> UC6 : <<include>>
    }

    note right of UC2: 包含富文本编辑、标签管理、草稿保存
    note left of UC7: 含数据看板、内容审核、系统监控
```
