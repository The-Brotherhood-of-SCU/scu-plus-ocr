## 如何部署

```bash
# 启动OCR服务（需Python环境）
cd ./ocr_server/python
python server.py
```
1. 进入插件设置 → 网络设置
2. 输入API地址：`http://localhost:[port]/ocr`
3. 测试连接 → 保存配置

\*：其实我们的OCR服务端有多种实现，如果有能力，我们更推荐使用**[Rust版](https://github.com/The-Brotherhood-of-SCU/scu-plus/tree/main/ocr_server)**

## ocr服务的其他实现

|名称|OCR库|HTTP版本|SSL支持|Note|
|:---:|:---:|:---:|:---:|:---|
|python|ddddocr|1.0|✅|简单易部署|
|rust|rten|1.1|❌|速度慢，效果差，不推荐|
|rust2|ddddocr-rust|2|✅|效率高速度快|

## HTTP协议
客户端发起POST请求
- POST /ocr

body
```json
{
    "img":"<base64>"
}
```
response
```json
{
    "result":"<ocr result>"
}
```

