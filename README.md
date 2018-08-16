# mybatis-generator-final
简单好用的支持lombok

AnnotationPlugin 和LombokPlugin 都继承了PluginAdapter类是插件的扩展

AnnotationPlugin用于在mapper接口上添加@Mapper注解
LombokPlugin 用于支持Lombok 在bean 上添加@Data注解等
topLevelClass.addImportedType("lombok.Data");
        topLevelClass.addImportedType("lombok.ToString");

        topLevelClass.addAnnotation("@Data");
        topLevelClass.addAnnotation("@ToString");
        
 可以根据需要自己进行扩展。
 generatorConfig.xml中需要添加扩展插件引用如下
 <plugin type="plugins.LombokPlugin" >
			<property name="hasLombok" value="true"/>
		</plugin>
		<plugin type="plugins.AnnotationPlugin">
			<property name="annotationClass" value="org.apache.ibatis.annotations.Mapper" />
			<property name="annotationName" value="@Mapper" />
		</plugin>
