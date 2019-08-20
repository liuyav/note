## ui 框架选型
1. 维护团队
2. 更新迭代
3. Github
4. 测试
5. 缺点
6. 特点

## ui 框架
1. cube-ui（移动端、后编译、create-api）
2. vant（ssr、ts）
3. element ui（pc）

## 路由守卫
1. 路由生命周期 beforeEach，全局守卫，在每个路由进来的时候，都有机会判断一下
2. 这时候看路由元数据里面有没有需要判断的元数据
3. 拿出token，有的话通行，否则，登录

## 登录状态保存
保存 token 在 localStorage 中

## 令牌机制
**Bearer Token规范**
1. 概念：描述在 http 访问和 OAuth2 保护资源时如何使用令牌的规范
2. 特点：令牌是身份证明，无需证明令牌的所有权
3. 具体规定：在请求头定义 Authorization
   - Authorization: Bearer token

**Json Web Token**
1. 概念：令牌具体定义方式
2. 规定：令牌由三部分构成“头、载荷、签名”
   - 头：包含加密算法，令牌类型的信息（base64编码，声明加密规则）
   - 载荷：包含用户信息、签发时间和过期时间等信息（base64编码）
   - 签名：根据头、载荷及密钥得到的hash串
3. 默认加密算法 Hmac Sha1 256（hs256）

## 请求拦截响应器

**请求拦截器**
请求之前，把 token 带上

**请求响应器**
请求之后，把

