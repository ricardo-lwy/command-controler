Lettre suivi 图像处理 -create by Weiyi LIU

平台：shopify+matrixify
目的：两个功能
1：实现将邮票的合并pdf拆分成子的邮票并且将其命名为它的运单号

2：将一小张邮票与我们的excel对应订单相匹配,生成拼接好的邮票和对应的输出结果excel

注意事项
1.对于pdf2sepimg文件，在运行前我们需要进入程序输入文件名（在第一行的input中可以看到）。

正常下载的pdf文件名是 vosTimbres+今天日期。日后可以通过这一点把这个程序封装起来
2.对应souimg2comtibres文件，同样要在运行前输入excel的文件名和sheetname

此程序有两个block，运行第一个block可以看到在程序完成以后还剩下多少张图片，如果图片数少于订单所需图片数则会警报
对应input的excel顺序：id-name-firstname-lastname-nowadr-nowadr2-citycode-city-country...(后面的是trackingcompany和trackingnumber什么的)
最后文件的遍历后顺序还要再进行一遍才可以得出最终结论
使用方法
1.实现第一个功能：整张邮票的pdf切割

【1】先将邮票的pdf文件上传到此程序下的./pdfs/文件夹下

【2】打开18112022pdf_2_sep_img.ipynb文件，在第一个代码块的input区域（前面几行可以找到）。将pdfname 这个变量名换成之前放入的pdf名字，然后点左上角运行即可。出来的结果就是分割以后的子图

2.实现第二个功能：将邮票与excel拼接生成结果excel与结果pdf


【1】将Orders的excel文件（注意！千万不要打开它）放在此程序(19112022sousimg_2_comtibres.ipynb)所在的文件夹

【2】点开此程序（19112022sousimg_2_comtibres.ipynb），将第一个代码块中的 excelname名字改成之前所放的excel名字

【3】点第一个代码块左上角的运行按钮运行程序，在这个代码块运行完毕以后可以看到预计运行完成以后还剩余多少张图片，如果邮票数不够则会发出警告

【4】在确认完预计剩余图片以后，依次点击第二个和第三个代码块（测试以及草稿文件前面）直到程序运行完成即可

【5】最终结果：打开原来的excel文件可以发现它已经被修改成拼接邮票以后的格式，可以直接用于上传。在./res-image/文件夹中可以找到该excel对应的文件夹，将其点开滑到最下面的merge.pdf文件此为用于打印的文件
tips
excel名字最好符合之前的规范日+月+年，便于日后复查

生成的结果excel文件以后如果确认无误就将其放入finished_order文件夹里面
