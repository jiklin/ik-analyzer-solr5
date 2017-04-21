# ik-analyzer-solr5

扩展 ik 源码，支持实时加载词典。

> solr5.5.3 测试通过

## 配置

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd">  
<properties>  
  <comment>IK Analyzer 扩展配置</comment>
  <!--用户可以在这里配置自己的扩展字典 -->  
  <entry key="ext_dict">custom/mydict.dic;custom/single_word_low_freq.dic</entry>   
   <!--用户可以在这里配置自己的扩展停止词字典-->
  <entry key="ext_stopwords">custom/ext_stopword.dic</entry>
  <!--用户可以在这里配置远程扩展字典 --> 
    <entry key="remote_ext_dict">http://localhost:8080/web/ext.dic</entry>
  <!--用户可以在这里配置远程扩展停止词字典-->
  <!-- <entry key="remote_ext_stopwords">words_location</entry> -->
</properties>
```

## 注意

`remote_ext_dict` 配置更新机制基于 http 响应头 `ETag` `Last-Modified`