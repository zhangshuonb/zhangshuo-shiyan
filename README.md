# zhangshuo-shiyan
一、 实验目的
1.	掌握字符串String及其方法的使用
2.	掌握文件的读取/写入方法
3.	掌握异常处理结构 二、 文件处理部分要求 在某课上,学生要提交实验结果，该结果存储在一个文本文件A中。 文件A包括两部分内容：
4.	学生的基本信息；
5.	学生处理后的作业信息，该作业的业务逻辑内容是：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能方法，实现如下功能：
1.	每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
2.	允许提供输入参数，统计古诗中某个字或词出现的次数
3.	输入的文本来源于文本文件B读取，把处理好的结果写入到文本文件A
4.	考虑操作中可能出现的异常，在程序中设计异常处理程序
三、 学生类部分要求：
1.	设计学生类（可利用之前的）；
2.	采用交互式方式实例化某学生；
3.	设计程序完成上述的业务逻辑处理，并且把“古诗处理后的输出”结果存储到学生基本信息所在的文本文件A中。 四、 实验流程
4.	建立学生类，要求如下：
1.	设立带有修饰符private的字符串型变量name，number，team
2.	创建变量对应的set与get函数，用来赋值与获取
3.	利用toString来复写学生类，方便后面的写入文件 五、 核心代码 以下代码展示了Java如何读取文件，如何处理文件中的字符串，利用字节流来读取文件，以及用字符流来将字节转换为字符，并将字符流存储在字符型数组中，并结合数组下标来将处理好的字符赋值在动态字符串中
四、核心代码

        try {
            FileReader fileReader = new FileReader("E:\\test.txt");
            BufferedReader bufferedReader = new BufferedReader(fileReader);
            Writer writer = new FileWriter(new File("E:\\123.txt"));
            String str = bufferedReader.readLine();
            String regex = "(.{7})";
            str = str.replaceAll(regex, "$1，");
            StringBuffer x = new StringBuffer(str);
            for (int  i = 15; i <289; i = i + 17) {
                x.replace(i, i + 1, "。\n");
            }
            System.out.println(x);
            writer.write(String.valueOf(xuesheng));
            writer.write("\n");
            writer.write(String.valueOf(x));
            bufferedReader.close();
            fileReader.close();
            writer.close();
        } catch (IOException e) {
            e.printStackTrace();
        } catch (Exception e) {
            System.out.println("出现错误!");
        }
 
五、核心方法： 1，利用scanner方法来进行交互输入 2，在bufferedReader方法中读取，存储文件 3，异常处理 4，for()循环去筛查用户的查询字 5，indexOF()方法查找字符串中某一字符的查找。

六、实验感想: 通过本次实验进一步掌握了异常处理的使用方法，学会replace方法将字符串替换为空的方法， 基本掌握字符串Sring的读和写入的方法，对于scanner的函数实例化更加理解，但在本次实验 过程中仍出现很多的问题，通过互联网和询问同学的形式，逐一解决了问题，本次实验不仅 磨练了我的耐心，也让我明白集思广益和团结互助的重要性，使我对Java的学习更有信心

