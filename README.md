### hive-exec-shaded
hive-exec-shaded used to generate a hive-exec-shaded.jar to be used in flink-hive integration


这个项目主要是为了解决Hive3.1.2版本自带的 hive-exec.jar ，在于flink集成时遇到的问题。

项目本身不包含任何代码，在pom.xml中使用 maven-shade-plugin 插件，将 com.google.* 相关的类重命名路径后再打包。

为了保持修改后的 hive-exec-shaded.jar 与之前的 hive-exec.jar 大小差不多。
hive-exec-shaded.jar 在插件 maven-shade-plugin 中，比对原有的 hive-exec.jar 的内容进行打包，保证两个jar的内容相差不大

Flink 与 Hive 的集成，见项目：