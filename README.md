# qiao.ext.oss
---
nodejs ali oss upload tool

# config.json
---
    {
		"region"			: "your region",
		"accessKeyId"		: "your access key id",
		"accessKeySecret"	: "your access secret",
		"bucket"			: "your bucket"
	}

# upload file and upload folder demo
---
	var qiaoExtOss 			= require('qiao.ext.oss');
	var qiaoExtOssConfig	= require('./config.json');
	
	var client = qiaoExtOss.client(qiaoExtOssConfig);
	
	/**
	 * upload file demo
	 * upload d:/test.js to your bucket's test/test.js
	 */
	qiaoExtOss.uploadFile(client, 'test/test.js', 'd:/test.js', function(err, rs){
		if(err) throw err;
		
		console.log(rs);
	});
	
	/**
	 * upload folder
	 * upload d:/test folder's files to your bucket's test folder
	 */
	qiaoExtOss.uploadFolder(client, 'test', 'd:/test', function(err, rs){
		if(err) throw err;
		
		console.log(rs);
	});

# version
---
### 0.0.2.20171213
1. 删除无关文件
2. 添加npmignore
3. 更新readme文件
4. exports

### 0.0.1.20171212
1. 初始化项目
2. 添加gitignore文件