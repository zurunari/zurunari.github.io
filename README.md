Genshin Team Paring

（伤害轴功能）
[~b0.3为止更新]
- 
- 增加了伤害轴可视化
![](src/assets/demo/界面介绍.png)
描述了20s的伤害轴中，谁应何时上场、Q/E技能timing和持续时间、以及伤害，分别用散点、堆积图和趋势线表示。靠上的堆积图表示E技能释放timing和持续时间，靠下的堆积图表示Q技能释放timing和持续时间。散点代表当前场上角色，切人的逻辑在DCcalc()方法中有描述。趋势线代表伤害估算，比如图里趋势线第一个波峰是四人都开大所致，趋势线前半段较高，因为万叶Q技能在生效中（攻击型辅助的大招一律简化为增伤）。3.4添加了基础伤害，即什么技能都不开只平A的伤害，用于展现开技能能带来多少伤害增幅

- 把角色界面和team界面里的card高度都定死了，解决了分辨率导致有时候缺一块的现象

- 换了个logo，用ba风格生成器弄的便宜logo，synergy在游戏里代表游戏配合，就用了这个词

- 存在的问题：
    - ~~伤害轴数据系列有时候会莫名其妙多出几个对象，表现为横轴不止20秒或者q/e技能状态缺失。用控制台看过，出bug时数据没问题，伤害曲线也没有受影响，像是显示的问题，重新编译就恢复正常了。真正原因还不知道~~
    （3.4已解决，是缓存问题，经过简单测试，不会再出现以上现象）
    - 左边的雷达图有超量程的风险，但由于算法太复杂一时不知道最极端情况是多少


[b0.4更新]
- 
- 修复了q技能会显示在e技能轴上的bug，由于周期不能两边都是开区间，伤害轴调整成0-19秒区域