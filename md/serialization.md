### 为了优化解析 JSON 与序列化 JSON 输出的过程，Fastify 可以[序列化数据](https://github.com/fastify/docs-chinese/blob/master/docs/Validation-and-Serialization.md)

我们可以在`schema`的选项中设置 `response` 的值，能够加快 JSON 的序列化

> 约束200状态码的response的数据格式

```js
const opts = {
  schema: {
    response: {
      200: {
        type: 'object',
        properties: {
          hello: { type: 'string' }
        }
      }
    }
  }
}
fastify.get('/', opts, async (request, reply) => {
  return { hello: 'world' }
})
```