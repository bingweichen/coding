# restful api

# resource
http://blog.gusibi.com/post/build_restful_api_by_swagger/

# 概念
- 资源（Resource）：系统上的所有事物都被抽象为资源（一篇文章，一张照片，一段语音）
- 集合（Collection）：一组资源的合辑称为集合（几篇文章，几张照片）
- 路径（Endpoint）：路径又称”终点“，表示API的具体网址（每个网址代表一种资源）

## API地址和版本
在url中指定API版本。比如：
``https://apis.gusibi.com/v1``

## 以资源为中心设计URL
```$xslt
users/:username/repos
/users/:org/repos
/repos/:owner/:repo
/repos/:owner/:repo/tags
/repos/:owner/:repo/branches/:branch
```

## Method
- GET：从服务器取出资源
- POST：在服务器新建一个资源
- PUT：在服务器更新资源（客户端提供改变后的完整资源
- PATCH：在服务器更新资源（客户端只提供改变了属性）
- DELETE：从服务器删除资源

```$xslt
GET /repos/:owner/:repo/issues
GET /repos/:owner/:repo/issues/:number
POST /repos/:owner/:repo/issues
PATCH /repos/:owner/:repo/issues/:number
DELETE /repos/:owner/:repo
```

## 正确的过滤信息

- ?limit=10: 指定返回记录的数量
- ?offset=10：指定返回记录的开始位置
- ?page=2&per_page=100：：指定第几页，以及每页的记录数。
- ?sortby=name&order=asc：指定返回结果按照哪个属性排序，以及排序顺序。
- ?animal_type_id=1：指定筛选条件
