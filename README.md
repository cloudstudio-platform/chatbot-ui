# Chatbot UI

Chatbot UI 是一个用于AI模型的开源聊天UI

查看[演示](https://twitter.com/mckaywrigley/status/1640380021423603713?s=46&t=AowqkodyK6B4JccSOxSPew).

![Chatbot UI](./public/screenshots/screenshot-0402023.jpg)

## 更新

Chatbot UI 将随着时间的推移而更新

期待接下来频繁的改进

**接下来:**

- [ ] 分享
- [ ] "机器人"

## 部署

**Vercel**

使用vercel托管您的实时版本的聊天机器人UI

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fmckaywrigley%2Fchatbot-ui)

**Docker**

本地构建:

```shell
docker build -t chatgpt-ui 
docker run -e OPENAI_API_KEY=xxxxxxxx -p 3000:3000 chatgpt-ui
```

从 ghcr 拉取:

```
docker run -e OPENAI_API_KEY=xxxxxxxx -p 3000:3000 ghcr.io/mckaywrigley/chatbot-ui:main
```

## 本地运行

**1. 克隆仓库**

```bash
git clone https://github.com/mckaywrigley/chatbot-ui.git
```

**2. 安装 Dependencies**

```bash
npm i
```

**3. 提供 OpenAI API Key**

使用您的OpenAI API在存储库的根目录中创建一个 .env.local 文件:
```bash
OPENAI_API_KEY=YOUR_KEY
```

> 您可以设置 `OPENAI_API_HOST` 对官方OpenAI主机的访问受到限制或不可用,从而允许用户根据自己的特定的需求配置替代主机

> 此外,如果您有多个OpenAI组织,您可以设置`OPENAI_ORGANIZATION` 为指定一个

**4. 运行应用程序**

```bash
npm run dev
```

**5. 使用它**

您可以开始跟它聊天了

## 配置

部署应用程序时,可以设置以下变量环境:

| Environment Variable              | Default value                  | Description                                                                                                                               |
| --------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| OPENAI_API_KEY                    |                                | 用于 OpenAI 身份验证的默认 API 密钥                                                                                   |
| OPENAI_API_HOST                   | `https://api.openai.com`       | 基于 url, 供 Azure 使用 `https://<endpoint>.openai.azure.com`                                                                         |
| OPENAI_API_TYPE                   | `openai`                       | API选项, 选项为 `openai` 或 `azure`                                                                                             |
| OPENAI_API_VERSION                | `2023-03-15-preview`           | 仅适用于 Azure OpenAI                                                                                                          |
| AZURE_DEPLOYMENT_ID               |                                | Azure OpenAI 时需要，参考[Azure OpenAI API](https://learn.microsoft.com/zh-cn/azure/cognitive-services/openai/reference#completions) |
| OPENAI_ORGANIZATION               |                                | 您的 OpenAI 组织 ID                                                                                                               |
| DEFAULT_MODEL                     | `gpt-3.5-turbo`                | 新对话中使用的默认模型，供 Azure 使用 `gpt-35-turbo`                                                               |
| NEXT_PUBLIC_DEFAULT_SYSTEM_PROMPT | [看这里](utils/app/const.ts) | 用于新对话的默认系统提示                                                                                     |
| NEXT_PUBLIC_DEFAULT_TEMPERATURE   | 1                              | 新对话使用的默认温度                                                                                       |
| GOOGLE_API_KEY                    |                                | 请看[自定义搜索 JSON API 文档][GCSE]                                                                                          |
| GOOGLE_CSE_ID                     |                                | 请看 [自定义搜索 JSON API 文档][GCSE]                                                                                          |

如果您不提供 OpenAI API 密钥 `OPENAI_API_KEY`, 用户将必须提供自己的密钥
如果您没有 OpenAI API 密钥，可以 [在此处](https://platform.openai.com/account/api-keys)获取

## 联系

如果您有任何疑问,请随时在Twitter上联系[Mckay](https://twitter.com/mckaywrigley).

[GCSE]: https://developers.google.com/custom-search/v1/overview

