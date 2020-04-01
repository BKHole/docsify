<!--
 * @Description:
 * @Author: libotao
 * @Date: 2020-04-01 16:00:54
 * @LastEditTime: 2020-04-01 16:14:31
 -->

# github 搜索指南

关键词+限制参数

## 搜索命令

- in:name xxx // 按照项目名搜索
- in:readme xxx // 按照 README 搜索
- in:description xxx // 按照 description 搜索
- stars:>xxx // stars 数大于 xxx
- forks:>xxx // forks 数大于 xxx
- language:xxx // 编程语言是 xxx
- pushed:>YYYY-MM-DD // 最后更新时间大于 YYYY-MM-DD

## example

```code
React stars:>1000

in:name React

in:name React stars:>1000

in:name React stars:>1000 forks:>300

in:readme React stars:>3000 forks:>300

in:description 微服务 language:python

in:description 微服务 language:python pushed:>2020-01-01
```
