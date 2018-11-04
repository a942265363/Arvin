# SpringBootJSP
Spring boot整合JSP开发
	之前spring boot默认 自带一个内置的tomcat，不需要打war包，直接通过Jar即可运行。


	但是，如果要整合jsp开发，就需要 单独配置一个 外置的tomcat ，需要打war包。
	Spring boot整合JSP开发步骤：
		1.新建boot项目， war		
			注意：
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-tomcat</artifactId>
			<scope>provided</scope>
		</dependency>
				provided：意思是 将项目打包时，不需要将内置的tomcat一起打包。

		2.建立基本的web项目所需要的目录结构
			webapps/WEB-INF(需要)
			webapps/WEB-INF/web.xml (不需要)
			webapps/index.jsp
		3.创建tomcat实例、部署项目	
		访问：
		域名：端口/项目名/文件名
		http://localhost:8080/SbJSP/index.jsp


		分析：
		如果是一个war包的spring boot项目，在启动服务器tomcat时， 会自动调用ServletInitializer类中 的configure方法，configure方法会调用spring boot的主配置类 从而启动spring boot;
		即在启动tomcat服务器时  会1启动tomcat  2启动spring boot
