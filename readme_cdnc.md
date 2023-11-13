
一、怎么连接到cdncloud的7牛云
    Config 增加私有化的配置项

#===============================================
    cfg := storage.Config{
		UseHTTPS: true, // 如果是http的url 这个参数为false 
		RsHost:   "https://rs.xxx.com",
		RsfHost:  "https://rsf.xxx.com",
		UpHost:   "https://up.xxx.com",
		ApiHost:  "https://api.xxx.com",
		IoHost:   "https://io.xxx.com",
	}
#===============================================

	mac := auth.New(accessKey, secretKey)

	bucketManger := storage.NewBucketManager(mac, &cfg)

    这样就可以用 bucketManger 去访问对应的资源了 
