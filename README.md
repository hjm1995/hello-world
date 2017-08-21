# java笔记
##### 数据结构与算法

* [算法分析的正确姿势](http://www.cnblogs.com/absfree/p/5464779.html)
* [算法精粹](https://www.gitbook.com/book/soulmachine/algorithm-essentials/details)
* [数据结构与算法设计](https://suanfa.herokuapp.com/0preface/)
* [fastjson 使用方法，打印JSON的方法](http://blog.csdn.net/zeuskingzb/article/details/17468079)
* [angluar ui-grid的api](http://ui-grid.info/docs/#/tutorial/214_pagination)
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
《2》、在做ui-grid的分页跳转时，当时想到的是先去查询了api。在查询过程中，发现没有满足自己想要的api时，我又去看了表格发起请求时转递的参数，然后就发现表格发起请求时会把页码给传过去，比如第一页传1，第二页传2，这样我就去查询语句的地方去接收这个参数，用来判断第几页，通过计算得出应该显示的是什么数据，结合《1》，得出正确的sql语句，完成分页跳转.
