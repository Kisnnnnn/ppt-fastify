## 就如同在 JavaScript 中一切皆为对象，在 Fastify 中，一切都是插件 (plugin)。

-n-

新建一个基础的插件

```js
// my-first-pugin.js
async function routes (fastify, options) {
  fastify.get('/', async (request, reply) => {
    return { hello: 'world' }
  })
}

module.exports = routes
```

在服务器上注册这个插件

```js
const fastify = require('fastify')()

// 注册插件
fastify.register(require('./our-first-route'))
// 监听3000端口号，启动
fastify.listen(3000, function (err, address) {
  if (err) {
    fastify.log.error(err)
    process.exit(1)
  }
  fastify.log.info(`server listening on ${address}`)
})
```