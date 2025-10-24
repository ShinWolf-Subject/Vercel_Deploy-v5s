# 🔐 Vercel API Token Guide

This repository provides a quick and clear guide for developers to generate a personal API token from Vercel. The token is required to authenticate requests to the [Vercel REST API](https://vercel.com/docs/rest-api).

## 📦 What’s Inside

- Step-by-step instructions to create your token
- Example usage with curl and Node.js
- Security tips for managing your token

## 🚀 How to Get Your Token

1. **Log in to Vercel**
   - Go to [vercel.com/account](https://vercel.com/account)

2. **Navigate to the Tokens Section**
   - Click on the “Tokens” tab in the sidebar

3. **Create a New Token**
   - Click “Create Token”
   - Name your token (e.g., `my-deploy-script`)
   - Click “Create” and copy the token immediately

4. **Store It Securely**
   - Save the token in an environment variable or secrets manager
   - Example:
     ```bash
     export VERCEL_API_TOKEN=your_token_here
     ```

## 🧪 Example Usage

Using curl:

```bash
curl -H "Authorization: Bearer $VERCEL_API_TOKEN" https://api.vercel.com/v2/projects
```

Using Node.js

```js
const fetch = require('node-fetch');

const response = await fetch('https://api.vercel.com/v2/projects', {
  headers: {
    Authorization: `Bearer ${process.env.VERCEL_API_TOKEN}`,
  },
});
const data = await response.json();
console.log(data);
```
