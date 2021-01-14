# trans
Android studio 语言翻译插件
使用方式:
1、在项目级别的build.gralde中

buildscript {

    repositories {
        google()
        jcenter()

        maven {
            url uri("http://nexus.tttinner.com:8888/nexus/content/repositories/releases/")
            credentials {
                username = "adsreach"
                password = "adsreach123"
            }
        }
    }
    dependencies {

        classpath 'com.language.trans:plugin:1.0.6'

    }
}
2、在module的build.gradle中
在Moudle级别的build.gradle中（一般是在app下边）

apply plugin: 'com.trans.plugin'

trans {
    //(配置目标语言,可配置多个目标语言)
    targetLanguage = ['en', 'jp'] 
}

当前可支持语言包括(
auto, // 自动检测语种
zh, // 中文
en, // 英语
jp, // 日语
fra, // 法语(最好不要使用)
kor, // 韩语
de, // 德语
ru, // 俄语
)

3、使用方式
1、在gradle中找到当前module任务，在other中，找到trans任务，点击执行





2、在命令行界面执行 gradle trans
