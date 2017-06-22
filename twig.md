## TWIG 模板引擎

* 获取 request 中的get信息
> {{ app.requet.get('parameter_name') }}

* 控制文本内容
> {{ c.title|length > 50 ? c.title|slice(0, 50) ~ '...' :c.title  }}

> {{ istr.informantSituation|truncate(12,false,'...')|default('暂无数据') }}