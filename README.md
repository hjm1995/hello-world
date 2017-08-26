# java笔记
##### 数据结构与算法

* [算法分析的正确姿势](http://www.cnblogs.com/absfree/p/5464779.html)
* [算法精粹](https://www.gitbook.com/book/soulmachine/algorithm-essentials/details)
* [数据结构与算法设计](https://suanfa.herokuapp.com/0preface/)
* [fastjson 使用方法，打印JSON的方法](http://blog.csdn.net/zeuskingzb/article/details/17468079)
* [angluar ui-grid的api](http://ui-grid.info/docs/#/tutorial/214_pagination)
* [URL传值符号转换](http://ghouleye.iteye.com/blog/704480)
* [样式表中的 element.style样式如何修改](http://blog.csdn.net/chenguang79/article/details/46721971)
<br/>
在js的循环中。如果要合并的时候没，可以循环这个数值对象。看有多少次，然后计算出要合并的几次。在循环的结果中可以删减已循环的对象。这样可以加快循环。不用每次都去循环。浪费时间，但在删减的过程中要注意索引。要重置索引，当然在第二次可能中的循环也要的，看情况而定比如
<br/>
 function merge(mergeList) {/*合并街道 与 合并社区 数据处理*/
            var array = mergeList.concat();
           for (var j = 0; j < array.length; j++) {

                var name = array[j].STREET;
                var num = 0;
                for (var i = 0; i < array.length;) {
                    if (array[i].STREET == name) {
                        num++;
                        array.splice(i, 1);
                        j=0;
                    } else {
                        i++;
                    }
                }
                for (var k = 0; k < mergeList.length; k++) {
                    if (mergeList[k].STREET == name) {
                        mergeList[k].STREET_NUM = num;
                    }
                }

            }
            array = mergeList.concat();
            for (var j = 0; j < array.length; j++) {
                var name = array[j].COMMUNITY;
                var num = 0;
                for (var i = 0; i < array.length;) {
                    if (array[i].COMMUNITY == name) {
                        num++;
                        array.splice(i, 1);
                        j=0;
                    } else {
                        i++;
                    }
                }
                for (var i = 0; i < mergeList.length; i++) {
                    if (mergeList[i].COMMUNITY == name) {
                        mergeList[i].COMMUNITY_NUM = num;
                    }
                }
            }
        }


《0》、在有一些提示org....的报错的时候，就是没有jar，需要下载。如右键项目mave中的reimport来刷新下载。<br/>
《1》、在表格中的分页。如果用sql的话就用limit。比如当前显示10条数据。如果下一页的话，那就是limit 10,10。如果是20条的话。就是limit 20,20下一页就是翻一倍，如40,20这就是第三页了。<br/>
《2》、在做ui-grid的分页跳转时，当时想到的是先去查询了api。在查询过程中，发现没有满足自己想要的api时，我又去看了表格发起请求时转递的参数，然后就发现表格发起请求时会把页码给传过去，比如第一页传1，第二页传2，这样我就去查询语句的地方去接收这个参数，用来判断第几页，通过计算得出应该显示的是什么数据，结合《1》，得出正确的sql语句，完成分页跳转.<br/>
《Hibernate的记错笔记》<br/>
（1）、在用hql查询时，select查询的不是数据库的表，而是实体类<br/>
《sql的常用笔记》<br/>
(1)在查询关联多个表时，只显示其中一个表的数据时可以用表名.*来表示。<br/>
《dialog弹窗的常用笔记》<br/>
（1）在使用dialog弹窗时。弹窗是模态的弹窗，所以要自定义弹窗时，个弹窗里面的是模态html，就是自己写的html。比如<br/>


{
        <script type="text/template" id="testTemplate">
            <div class="modal-content" style="height:380px;width:780px;padding:9px;">
                <#--<div class="modal-header">
                    <button type="button" class="close" ng-click="cancel()" aria-hidden="true">
                        &times;
                    </button>
                    <h4 class="modal-title" id="myModalLabel">若地图不显示，请刷新后重试</h4>
                </div>
                <div class="modal-body">
                    <div style="width: 100%;height: 620px;">
                      dfjhfgdghfjhfdghfdghfjhfgjkgjk
                    </div>
                </div>-->
				<#include "/index/admin/WeChatWin.html"/>
            </div>
        </script>
	}
   在<scropt>的标签中就是你定义的html页面。在用弹窗时只需要给id就可以了，比如<br/>
     $rootScope.winWeChat=function () {//打开微信扫二维码下载
           dialog.open('#testTemplate');
       }<br/>
	<h4>《angularjs的常用笔记》</h4><br/>
(1)、在使用ng-click时，有时会发生作用域的问题，使得点击按钮会没有反应。解决方法，1、在创个div把这个ng-click包起来给个ng-controller指向方法的所在controller

