# springboot-redis-cache-gradle
 基于gradle构建缓存项目。缓存使用redis.缓存框架使用spring缓存框架。相关点有：
 * springboot
 * redis : 提供缓存功能
 * gradle : 做为打包，构建工具
 
## gradle install
相当于mvn install。可以打包到本地仓库。
相关配置为：
```
// best way to set group ID
group = 'com.niejinkun.spring'

install {
    repositories.mavenInstaller {
        // only necessary if artifact ID diverges from project name
        // the latter defaults to project directory name and can be
        // configured in settings.gradle
        pom.artifactId = 'springrediscachegradle' 
        // shouldn't be needed as this is the default anyway
        pom.packaging = 'jar'
        
        pom.version = '0.0.1'
    }
}
```

其中，仓库配置为：
```
repositories {
  mavenLocal()
  mavenCentral()
  maven { url "https://repo.spring.io/libs-release" }
}
```

依赖的maven插件为
```
apply plugin: 'maven'
```

springboot插件为：
```
apply plugin: 'spring-boot'
```

## 打包
```
gradle install
```

## 运行
```
gradle bootrun
```
