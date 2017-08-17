# java笔记
##### 数据结构与算法

* [算法分析的正确姿势](http://www.cnblogs.com/absfree/p/5464779.html)
* [算法精粹](https://www.gitbook.com/book/soulmachine/algorithm-essentials/details)
* [数据结构与算法设计](https://suanfa.herokuapp.com/0preface/)
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


在有一些提示org....的报错的时候，就是没有jar，需要下载。如右键项目mave中的reimport来刷新下载。
