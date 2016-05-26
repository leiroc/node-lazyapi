# node-lazyapi
>基于 NodeJs + Express 4.xx + Mysql  建表、删表、增、删、查、改、排序、统计等API接口。

##接口说明

> 主机地址：HOST = 'http://v5cy.cn/core'

注意：
>带“可选”的是可选，不带的说明是必填项

-


>一、保存数据

- 请求URL： /us/save 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/save',
		data: {tabN: '表名', key1: '', key2: ''}
	})

```

- 说明： tabN: 是表名， 后面的 key 是自定义保存的字段；


>二、查找数据 （带PK主键）

- 请求URL： /us/query 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/query',
		data: {tabN: '表名', PK: '指定主键值'}
	})

```

- 说明： tabN: 是表名，PK 是大写的主键，必填；


>三、带条件查找数据 （where条件查询）

- 请求URL： HOST + /us/queryWhr 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: '/us/queryWhr',
		data: {tabN: '表名', whr: 'key1 = "value2" and key2 = "value2"'}
	})

```

- 说明： tabN: 是表名，whr ： 是条件值，注意 值需要 双引号 ""；


>四、修改数据

- 请求URL： HOST + /us/modify 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/modify',
		data: {tabN: '表名', PK: '指定修改的主键值',key1: '要修改的值', key2: '要修改的值'}
	})

```

- 说明： tabN: 是表名，PK 是大写的主键，必填, key1,key2 值要修改的字段；



>五、删除数据

- 请求URL： /us/delete 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/delete',
		data: {tabN: '表名', PK: '指定删除的主键值'}
	})

```

- 说明： tabN: 是表名，PK 是大写的主键，必填；


>六、获取数据

- 请求URL： /us/sort 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/sort',
		data: {tabN: '表名', topN: '一次获取数据长度，int 型', whr: '按条件查询(可选)', orderBy: '按照字段排序（可选）', orderType: '排序方式： asc|desc（可选）'}
	})

```

- 说明： tabN: 是表名，当有 orderBy 时，那么orderType就是必填；


>七、获取数据 (带自己的排名)

- 请求URL： /us/sort/me 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/sort/me',
		data: {tabN: '表名',PK: '主键值', orderBy: '按照字段排序', orderType: '排序方式： asc|desc'}
	})

```

- 说明： tabN: 是表名， orderBy，orderType 都是必填；



>八、分页获取数据

- 请求URL： /us/sort/page 
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/sort/page',
		data: {tabN: '表名',pageNo: '当前页数',  topN: '一次获取数据长度，int 型', whr: '按条件查询(可选)', orderBy: '按照字段排序（可选）', orderType: '排序方式： asc|desc（可选）'}
	})

```

- 说明： tabN: 是表名；



>九、统计总的数据条数（带条件）

- 请求URL： /us/count
- 方式： post
- 示例：

```
	
	$.ajax({
		url: HOST + '/us/count',
		data: {tabN: '表名',whr: '按条件查询(可选)'}
	})

```

- 说明： tabN: 是表名；

