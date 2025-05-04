

<div align="center"> <img src="https://github.com/Cunninger/ocr-based-qwen/blob/main/ocr.png?raw=true" width="120"> </div>



#               QwenLM OCR 


本项目基于 [QwenLM](https://chat.qwenlm.ai/) 。通过调用 QwenLM 的 ”API“，你可以从图片中提取文字内容，并且该项目支持一键部署到 **Cloudflare Workers** (CF) 上。

## 项目展示
![screely-1743379867339](https://github.com/user-attachments/assets/ad25719c-0504-4bc1-926f-4bffeb6b745d)


## 测试cookie
- 如果出现**处理失败: 文件上传失败的错误**，说明测试Cookie 上传文件过多, 尝试获取自己账号的Cookie 使用
```
{
    "code": "RateLimited",
    "detail": "Reached file upload limited: too many files uploaded in (86400.0) seconds."
}
```

![image](https://github.com/user-attachments/assets/5251feec-3fdc-4003-82b5-a273a3abb9f2)
- cookie1:
```txt
cna=pklJII7LlmACAWrjg1e7Aw5T; _bl_uid=vjmdq8ej4XLdptzy8g22cbqap10w; _gcl_au=1.1.2061498123.1740790694.1095090244.1742178801.1742178800; visitor_id=69d9708501480ef09203b791ac6bf725; x-ap=ap-southeast-1; xlly_s=1; acw_tc=0a03e53417425630262545566e597ceb582665688952129fe15ad53c13a1f9; ssxmod_itna=eq0xcD9DgDnDRQGG0K3qq7K7KqKqeTx0dGMD3Mq7tDRDFqAP5DHIOFP5DUgork7Dhx=80hqDsqQY4GzDiMPGhDBmAHQYDDKCYRhc0NPY1mT2DC1uhedHmd4N7ArjRr9ZZSrtexB3DEx0==nTirDYYEDBYD74G+DDeDir3Dj4GmDGA3deDFCmbQcnre=xDwDB=DmqG2Q2rDm4DfDDd5O7=jCWroDDtDAun1PPDADAfY24Dl08OjCGDK24GWClR/iceaMawdV2rDjdPD/RG021H2o5LtXCMs+9Ye=cWDtqD986RVWaIYVQu4wIYCDqQRDPhFCIYQDblxx8DFnD47DtGA4YiiGGbjaHCGKR+63+FQwFe9x=EF7Dh+5ZUvwRy/exxfRDAuCjEYeeCtGqCIOlgtCiN/riQGQ=G4WGeuricqFeD; ssxmod_itna2=eq0xcD9DgDnDRQGG0K3qq7K7KqKqeTx0dGMD3Mq7tDRDFqAP5DHIOFP5DUgork7Dhx=80o4DW+DDwYpQkUCgDCMCnMHiqezU=ED; SERVERID=7f8d8d352ef7abbfd818d506cbe1b627|1742563117|1742563026; token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjUzZTk0Nzg4LWMwM2QtNDY4Mi05OTNhLWE0ZDNjNGUyZDY0OSIsImV4cCI6MTc0NTE1NTExN30.4g_Jz3Gv_OmBRMSJVoy641H9iCG90v39SK18wu9mCFQ; tfstk=ga7qs-x4urU2V1_4IQYZ4vDR3xTvJE2I0N96s1fMGKv0HNTwsL5Zhi11sFzwEExOcd9XQF5OL7wQRy1AMFpgdJaCSmqqdFpg5FqWr_hjUk2QRy1cFK8BDJ_jwASyHCYMihAmq7R6tFADndVyECRKjxXMS7PysCHMid0Mr3ApEdYMSOfuaCMKRtBtdBx0_VcIk0DvMnJhiLuNMaRD0mCDUV0Gzt-2K29rSVbyM_MBBrgUfpjphHtPEzg27_ANhL63-48kYMC6_tzqoEsl2ZLfPJlp0OJyxatzrYRPz6sHw_rUa_7w3HbD4fgXoERGIhS8L2O2lg-FuiFtEsXB3MYA1XyfaHSyvQxo_mYfA6_9xZ4qpLtp_t95Ky0yrhjzLAdugA_O0AmwmQdyd7Pr8_lRpTUzeHmtX3xHapNvjcn9mQdyd7PrXcKx-QJQMhf..; isg=BA0NXKJIVjFc4PIC5ORdQdZ0HCmH6kG8OYRCyE-SSaQTRi34FzpRjFvAstogsll0
```
- cookie2:
```txt
acw_tc=c2db8f77aa0023a996777b8537356b308a98c7fb128b3020323ddd0d440fee2e; x-ap=ap-southeast-1; _gcl_au=1.1.485014960.1742563291; cna=2lVkIP9JX0cCAWrgu3Se+w7K; _bl_uid=L2mdt8wtidFtCg6hOwepuqdbswp9; xlly_s=1; ssxmod_itna=eqfx9DRDgDuCq4e9irD+x0xiIt4Kk0q0dGMD3u47t=GcD8xx0POD8ne5DUhKgGg5hxPY0hqDsPexiNDAg40iDCbmd87DDqtqgUb7DPmYRE7DtUgiz1dRuKOGrh2LROs=/Dc3eOieGLDmKDU2Dre34DxPPD5xDTDWeDGDD3rxGaDmeDe1ghD04mFfovifAoD7eDXxGCz74mDYPDWxDFibw8HxowrDDCDi5flb3DixiaTzPDB1PuHhDKtzPDEDOIVEfozBdqO/PmD7H3DlPx+vdXwH/asIoyso6r3+3fDCKDjgSpxSrQTKSI5b8+Dxn0YeWeOgO+GDYhxqDty+xKGKBB3Qix70DeDxoxxQGKgGw9xqQAYOEQOO7YCpOhKKbzcqsibslTe7G3qGtuOv+GiqB=klOpOAMA5KB5e35K+D3ixTQmkeh4D; ssxmod_itna2=eqfx9DRDgDuCq4e9irD+x0xiIt4Kk0q0dGMD3u47t=GcD8xx0POD8ne5DUhKgGg5hxPY0o4DW+DDwYpQkUCgDCMSOB5qeg0/mkbxD; token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImQ5MWIwY2ExLTlhZmMtNDkwNi05MTQ4LWNlN2M4ZjZhN2NmYyIsImV4cCI6MTc0NTE1NTMzM30.jqUN03CY_bB6GniWCn6ISQkdnpN59hm3Gug655Dd2GI; SERVERID=4c8b4dba95825d8ac7605fad188b7907|1742563334|1742563289; tfstk=gw6qcdO43-eqJr64S3vZa2mpW7vvhK4QnOT6jGjMcEY0kO9wjUSZlss1jdywrNLchdDirF7wXqADIjvZQUth1qDcmC8kjNO0DnVvQbx6fxcMISLZDT7ECxaYMGDwCd4QRJwCDgJ9Iy_g58eDkhIkSuO0iuwfud4QR8tK5z0vIZNRCkiPqUKwjjDcS3mkyhkisNYDZ4xevdYGSN0lqntsiAcDSYqyXUYMIdbMEvFVkN3BxIqZIcF3PztMgejDzASAUnAqMiYrIAXPuI8ndUkiIT-VVmR-AvP6-6LXOQ7uFxJNqh7XPw2nULAF9GtNu-kDh_fRHK678DdV7URhFQyoz3WPA6xR4WrP4O82ttArfx9D3hbM__UEdnJfaBWVMl3lmwTVtKIsYrsyT_RpqQmZiK1CAOdhn-upPBKNlU_3KYJksgkKW3qq5OCqSfRD238Q4u7onRcc_mCrKfh9ZBxyRodi6fdD238Q4ult6IHH4eZvs; isg=BLGxZSYScp1XxN6JZK3ED2FvwD1LniUQRPVRw5PFbniWutAM2e5m4VbM3k7cRr1I
```
## 🚀 功能特性

- **图片 OCR**：使用 QwenLM 强大的 OCR 功能从图片中提取文字。
- **拖拽上传**：直接将图片拖拽到页面即可识别。
- **复制粘贴**：支持从剪贴板直接粘贴图片进行识别。
- **Token 管理**：支持多 Token 轮询使用，提升稳定性。
- **历史记录**：保存每次识别的结果和图片，方便查看。
- **一键复制**：轻松复制识别结果到剪贴板。
- **数学公式识别**：特别优化了对数学公式的提取，支持 LaTeX 格式输出。
- **API 支持**：提供 `curl` 接口调用，支持通过图片文件、base64 和图片 URL 3种方式。(Apifox调用文档示例(**仅作为代码示例，这个网页调试有问题**)：https://0vkh6v4ad8.apifox.cn/)
- **验证码识别**：新增验证码识别功能，支持常见类型的验证码（如数字、字母、混合字符等），提升自动化处理能力。
- **自定义prompt**: 在高级模式下(v1.1.0支持)，用户可以自定义 prompt，跳过格式化处理，直接返回原始结果，而在普通模式下，使用默认的 prompt 并保持现有的格式化处理逻辑。
## qwen模型接口：
https://chat.qwenlm.ai/api/models
## 提示词工程
```
  const defaultPrompt =
    '不要输出任何额外的解释或说明,禁止输出例如：识别内容、以上内容已严格按照要求进行格式化和转换等相关无意义的文字！' + '请识别图片中的内容，注意以下要求：\n' +
    '对于数学公式和普通文本：\n' +
    '1. 所有数学公式和数学符号都必须使用标准的LaTeX格式\n' +
    '2. 行内公式使用单个$符号包裹，如：$x^2$\n' +
    '3. 独立公式块使用两个$$符号包裹，如：$$\\sum_{i=1}^n i^2$$\n' +
    '4. 普通文本保持原样，不要使用LaTeX格式\n' +
    '5. 保持原文的段落格式和换行\n' +
    '6. 明显的换行使用\\n表示\n' +
    '7. 确保所有数学符号都被正确包裹在$或$$中\n\n' +
    '对于验证码图片：\n' +
    '1. 只输出验证码字符，不要加任何额外解释\n' +
    '2. 忽略干扰线和噪点\n' +
    '3. 注意区分相似字符，如0和O、1和l、2和Z等\n' +
    '4. 验证码通常为4-6位字母数字组合\n\n' +
    '';
```
## 🛠️ 部署指南

### 1. 部署到 Cloudflare Workers

1. **配置 Cloudflare Workers**：
   - 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)。
   - 创建一个新的 Worker。
   - 将 `worker.js` 中的代码复制到 Worker 编辑器中。

2. **部署**：
   - 保存并部署 Worker。
   - 获取 Worker 的访问地址，即可使用。
### 2. Docker 一键部署
1. 使用以下命令拉取并运行Docker镜像。
```
docker pull sexgirls/qwen-ocr-app:latest
docker run -p 3000:3000 sexgirls/qwen-ocr-app:latest
```
2. 然后在浏览器中访问应用：
```
http://localhost:3000
```
详情可见：https://github.com/Cunninger/ocr-based-qwen/tree/docker-version
## 🧩 使用说明

1. **设置 Cookie**：
   - 前往 [QwenLM](https://chat.qwenlm.ai/) 获取对话请求中的 Cookie。
   ![alt text](image.png)

   - 点击右上角的 **⚙️ Cookie设置** 按钮。
   - 输入你的 Cookie（或者使用测试Cookie）。
   - 点击 **保存**。

2. **上传图片**：
   - 拖拽图片到页面，或点击上传区域选择图片。
   - 支持直接粘贴图片。

3. **查看结果**：
   - 识别结果会显示在页面下方。
   - 点击 **复制结果** 按钮，将识别内容复制到剪贴板。

4. **查看历史记录**：
   - 点击左侧的 **📋 识别历史** 按钮，查看历史识别记录。
   - 点击历史记录中的图片，可以查看大图。

5. **API 调用**：
   - **支持 base64**：
     ```bash
      curl -X POST \
        'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/base64' \
        -H 'Content-Type: application/json' \
        -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
        -d '{
          "base64Image": "YOUR_BASE64_IMAGE_STRING"
        }'
     ```
   - **支持图片 URL**:
     ```bash
      curl -X POST \
        'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/url' \
        -H 'Content-Type: application/json' \
        -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
        -d '{
          "imageUrl": "YOUR_IMAGE_URL"
     }'
     ```
6. **验证码识别**
![image](https://github.com/user-attachments/assets/66f24d52-6263-446c-b371-cc2e65c9277c)


## 📜 许可证

本项目基于 MIT 许可证开源。详情请查看 [LICENSE](LICENSE) 文件。

## 🙏 致谢

- 感谢 [QwenLM](https://chat.qwenlm.ai/) 提供的 OCR 功能。
- 感谢 Cloudflare 提供的 Workers 服务。

---

🌟 如果觉得这个项目对你有帮助，欢迎点个 Star 支持一下！🌟

**体验地址**：[智能图片识别 (doublefenzhuan.me)](https://ocr.doublefenzhuan.me/)

**GitHub 仓库**：[Cunninger/ocr-based-qwen](https://github.com/Cunninger/ocr-based-qwen)

---

#### 后续计划
- 优化数学公式识别精度；
- 增加更多 API 功能支持；
- 提升识别速度和稳定性。

快来体验吧！如果有任何问题或建议，欢迎在 GitHub 上提 Issue 或直接联系我！

## 更新
### 2025/01/13 应佬友需求，优化了对数学公式的识别，效果如下图
- 原图：
    
![image](https://github.com/user-attachments/assets/9841509d-be56-4eb9-aafa-4d4ca5555c2e)

- 识别效果图：
![image](https://github.com/user-attachments/assets/2340dc6d-9156-4866-aa53-cdfd1911a651)


### 2025/01/13 18点34分 支持`curl`接口调用
- **支持base64**：
```bash
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/base64' \
  -H 'Content-Type: application/json' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -d '{
    "base64Image": "YOUR_BASE64_IMAGE_STRING"
  }'
```
- 效果图：
![image](https://github.com/user-attachments/assets/363afb39-444b-4308-a2bd-55831df81b6f)

- **支持图片URL**:
```bash
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/url' \
  -H 'Content-Type: application/json' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -d '{
    "imageUrl": "YOUR_IMAGE_URL"
  }'
```
- 效果图：
![image](https://github.com/user-attachments/assets/a816085e-8a52-4425-b02c-94ea543bf95b)

- **通过图片文件识别（需要先上传获取imageId）**
```bash
# 1. 先上传文件
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/proxy/upload' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -F 'file=@/path/to/your/image.jpg'

# 2. 使用返回的imageId进行识别
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/recognize' \
  -H 'Content-Type: application/json' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -d '{
    "imageId": "RETURNED_IMAGE_ID"
  }'
```
## Cloudflare访问数据
![image](https://github.com/user-attachments/assets/bb456075-6107-47ee-a361-a0edba532c38)
## 致谢
![image](https://github.com/user-attachments/assets/cfc04290-6400-483d-b0a9-4dd4b409bab9)
## 趋势
[![Star History Chart](https://api.star-history.com/svg?repos=cunninger/ocr-based-qwen&type=Date)](https://star-history.com/#Cunninger/ocr-based-qwen&Date)
