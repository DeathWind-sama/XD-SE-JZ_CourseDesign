# 西电软工计组课设
微机原理实验也叫计组课设，这里的代码是被刘博迫害后的产物，可读性高，功能到位，鲁棒性好。

刘博会问一堆池沼问题，即使看懂每一行代码也然并卵。

## 第一次
ASCII是通过循环左移移到CF寄存器然后输出的。

缓冲区不能全部初始化成‘$’，而是要手动给字符串末尾加上‘$’（缓冲区的第二个字节就表示字符串长度，而字符串从第三个字节开始）。

##第二次
有的人可能写的用0AH输入字符串，但按照视频应当使用01H进行单个字符处理。

异常有三种：空输入（直接按下回车）、非数字、输入过多。都要处理。

要使用PUSH、POP来保护现场，把输入封装起来，避免影响已经存在AX里的数据。

积的高位是会存在DL里面的。计算结果是DL、AH、AL一起存的，记得都要进行保护。

由于最多是五位数字，因此最多也只会让DL的最低位变成1，也只有最后一次加有可能加出进位（CF=1）。