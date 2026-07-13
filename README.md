mermaid
graph TD
  A[系统上电初始化] --> B[液晶初始化、定时器0启动<br/>(设置2ms定时扫描)]
  B --> C[显示首屏 Welcome]
  C --> D[主循环开始]
  D --> E{new_key_flag == 1 ?}
  E -- 是 --> F[处理按键<br/>(process_key)]
  F --> G[标记重绘<br/>(flag_refresh = 1)]
  E -- 否 --> H{flag_refresh == 1 ?}
  H -- 是 --> I[清屏并刷新三行数据]
  H -- 否 --> J[喂狗/空闲]
  G --> H
  I --> J
  J --> D
