```mermaid
erDiagram
顾客 {
        varchar 姓名
        varchar 地址
        varchar 电话
        varchar 身份证号* 
    }
    会员卡 {
        varchar 号码*
        varchar 等级
        int 积分
    }
    顾客 ||--|| 会员卡 : "办理"


```