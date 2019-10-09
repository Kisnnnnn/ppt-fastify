# 如何创建一个简单的 Fastify 应用？

-n-

声明一个监听客户端`http://127.0.0.1:3000/`的「GET」请求

Fastify返回 `{ hello: 'world' }`。

```js
// 加载框架并新建实例
const fastify = require('fastify')({
  // 开始日志记录
  logger: true
})

// 声明路由
fastify.get('/', function(request, reply) {
  reply.send({ hello: 'world' })
})

// 启动服务！
fastify.listen(3000, function(err, address) {
  if (err) {
    fastify.log.error(err)
    process.exit(1)
  }
  fastify.log.info(`server listening on ${address}`)
})
```

-n-

#### 我们还可以利用`async/await`特性，讲Fastify进行异步操作 

```js
const fastify = require('fastify')()

fastify.get('/', async (request, reply) => {
  return { hello: 'world' }
})

const start = async () => {
  try {
    await fastify.listen(3000)
  } catch (err) {
    fastify.log.error(err)
    process.exit(1)
  }
}
start()
```