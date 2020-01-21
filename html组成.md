html的结构：
1、<!DOCPYPE html>声明用的
2、<html></html>定义起始和结束用的
3、<head></head>网页头:定义一些特殊内容用的，如页面标题、定时刷新、外部文件
     在此标签里面使用的六个常用标签：
     ①<title></title>  定义标题用的
     ②<meta  ...  />定义页面特殊信息，不显示，而是给引擎蜘蛛看的
           两个重要属性：
                    (1)name:
                           常用取值实例:(F1)<meta name="keywords" content="QYchanj"/>网页关键字
                                                  (F2)<meta name="description" content="QYchanj"/>网页描述
                    (2)http-equiv:
                        实例:(F1)<meta http-equiv="content-Type" content="text/html; charset=utf-8"/>
                   html5中简写<meta charset="utf-8"/>定义网页所使用的编码，这里定义使用utf-8
                   为了防止页面出现乱码，一般在每个html页面都要加这个，而且要加在其他meta标签前面
                                (F2)<meta http-equiv="refresh" content="6;url=http://www.baidu.com"/>
                                       定义网页六秒后自动跳转到http://www.baidu.com
     ③<link>用于引入外部css文件，先略过                  
     ④<style>定义元素的css样式，先略过
     ⑤<script>用于定义JavaScript，也可以引入外部JavaScript文件，先略过
     ⑥<base>没啥用的标签
4、<body></body>
  注释:<!-- -->
         
