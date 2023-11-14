一、怎么连接到cdncloud的7牛云

    Config 增加私有化的配置项
    ===============================================
```
    cfg := storage.Config{
		UseHTTPS: true, // 如果是http的url 这个参数为false 
		RsHost:   "https://rs.xxx.com",
		ApiHost:  "https://api.xxx.com",
		IoHost:   "https://io.xxx.com",
	}
```
    ===============================================
  
```
    // 用自己的ak，sk 验证
	mac := auth.New(accessKey, secretKey)
    // 用上面的 mac 和cfg 获取一个bucketManger 然后就能正常的操作了
    bucketManger := storage.NewBucketManager(mac, &cfg)
```
