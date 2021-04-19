windows 安装
参考文档： https://docs.spring.io/spring-boot/docs/2.1.7.RELEASE/reference/html/getting-started-installing-spring-boot.html#getting-started-manual-cli-installation
一。 安装前提
jdk 1.8
maven 

二。 安装springboot cli 
1. 下载springboot cli 包
https://repo.spring.io/release/org/springframework/boot/spring-boot-cli/2.1.7.RELEASE/spring-boot-cli-2.1.7.RELEASE-bin.zip

2. 解压到 D:\env\spring-2.1.7.RELEASE

3. 设定环境变量
SPRING_HOME
加入 SPRING_HOME/bin 到 PATH 下.

Environment Variables
---------------------
No specific environment variables are required to run the CLI, however, you may want to
set SPRING_HOME to point to a specific installation. You should also add SPRING_HOME/bin
to your PATH environment variable.

4. 开启cmd , 测试
spring --version

三。 编写第一个demo
app.groovy:  

@RestController
class ThisWillActuallyRun {

	@RequestMapping("/")
	String home() {
		"Hello World!"
	}

}


四。 启动应用

spring run app.groovy


五。 验证
http://localhost:8080/

