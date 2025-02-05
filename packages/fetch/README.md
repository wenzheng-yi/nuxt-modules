# @spruce-hub/nuxt-fetch

## Usage

```bash
npm install @spruce-hub/nuxt-fetch --save
# or
pnpm add @spruce-hub/nuxt-fetch -P
```

## Quick start

```ts
// nuxt.config.ts
export default defineNuxtConfig({
  modules: ['@spruce-hub/nuxt-fetch'],
  runtimeConfig: {
    nuxtFetch: {
      // 需要代理的路由前缀
      baseApi: '/api',

      // 从 cookie 中获取名为 access_token 的值并写入请求头 Authorization 中
      authorization: 'access_token',

      // 可选，最高优先级，从环境变量中获取目标服务地址
      apiHostEnv: 'API_HOST', // process.env.API_HOST

      // 可选，当 process.env[apiHostEnv] 为 false，从 apiHostUrl 获取目标服务地址
      apiHostUrl: 'http://myapi.com/',
    },
  },
})
```

```ts
const { data, pending, error, refresh } = await useFetch('/api/example')

// http://localhost/api/example => http://myapi.com/api/example
```

## License

[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2023-present, Spruce FE
