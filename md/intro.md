# 什么是 Fastify？

-n-

Fastify 是一个高度专注于以最少开销和强大的插件架构，为开发人员提供最佳体验的 Web 框架。

它受到了 `Hapi` 和 `Express` 的启发，是目前最快的 Node 框架之一。

`Fastify`  独特的将 `JSON Schema` 应用到请求时的 `validation` 和响应时的 `serialization`， 作者写的 `fast-json-stringify` 包更是达到了**2x faster than JSON.stringify**的神奇效果。

-l-

# 为什么要使用 Fastify

-n-

- 100％ 异步：框架的核心都是用`异步`代码实现的
- 高性能：每秒可以提供`34000`个请求
- 可扩展：Fastify 通过其`钩子`，`插件`和`装饰器`完全可扩展
- 基于模式：即使不是强制性的，我们建议使用 `JSON Schema` 来验证路由并序列化输出
- 日志记录：日志非常重要，但成本高昂,我们选择了最好的记录器 `Pino`
- 对开发者友好：该框架构建非常有表现力，不会牺牲性能和安全性
