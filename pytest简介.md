# 测试方案

**1.工具类：**

- postman
- jmeter
- soapui 

**2.代码类-现成框架-python**

- unittest---解释器自带框架
- pytest---高级--效率，定制化
- nose
- rf-封装关键字----*

**3.测试平台**

- 前端
- 后端
- 执行机制--框架pytest



# <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>Pytest框架简介</span>



Pytest是python的第三方单元测试框架，比自带unittest更简介和高效，

支持315种以上插件，同时兼容unittest框架，

在unittest框架迁移到pytest框架的时候不需要重写代码

## <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>1.pytest框架环境搭建</span>

### 环境搭建

**首先使用pip 安装pytest**

pip install  pytest

pip install pytest-html

**查看pytest是否安装成功**

pip show pytest

## <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>2.pytest执行测试用例</span>





总结一下：使用pytest执行测试需要遵行的规则：

- .py测试文件必须以test**开头**(**或者以**_test结尾)
- 测试类必须以Test开头，并且不能有init方法
- 测试方法必须以test开头、
- 断言必须使用assert



**执行 pytest文件实例**：

```python
import pytest
#1.定义函数类型---测试用例
def test_tc01():
    assert 1+1==2#断言
def test_tc02():
    assert 1+1==3#断言
if__name__=='__main__':
    pytest.main(['test_func01.py'])
    
#2.封装测试类
class TestLogin:#登录模块
    #该测试类-前置条件---初始化
    def setup_class(self):
        print('执行测试类之前，我需要执行操作-----')
    def test_login01(self):
        print('----test_login01----')
        assert 1+1 ==2#断言
    
    def test_login02(self):
        print('----test_login02----')
        assert 1+1 ==3#断言
    def teardown_class(self):
        print('-----该测试类环境清除’)
        
if__name__=='__main__':
    #需要打印的对应信息 -s
    pytest.main(['test_func01.py','-s'])
```



pytest中有四种setup和teardown:

1. <span style='color:blue;background:背景颜色;font-size:文字大小;font-family:字体;'>setup_module</span>和<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>teardown_module</span>在整个测试用例所在文件中所有的方法运行前和运行后运行，只会运行一次；
2. <span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>setup_class</span>和<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>teardown_class</span>在整个文件中的一个class中所有用例的前后运行
3. <span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>setup_method</span>和<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>teardown_method</span>在class内的每个方法运行前后运行
4. <span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>setup_function</span>，<span style='color:blue;background:背景颜色;font-size:文字大小;font-family:体;'>teardown_function</span>则在非class下属的每个测试方法的前后运行；

<span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>4.数据驱动</span>

## <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>3.文件新建</span>

1. **新建文件夹data-**---存放数据，如excel测试用例等等
2. **新建package包lib**----存放公共模块等
3. **新建package包test_case**---存放测试用例代码
4. **新建文件夹report**---存放报告

**备注：如果配置文件过多，过大，可新建package包config，存放配置文件**



## <span style='color:red;background:背景颜色;font-size:文字大小;font-family:体;'>4.数据驱动</span>

```python
#[(1,2),(3,4),(5,6)] [1,2,3]
#2.封装测试类
class TestLogin:#登录模块
    #该测试类--前置条件---初始化
    def setup_class(self):
        print('执行测试类之前，我需要执行操作-----')
        
    @pytest.mark.parametrize('a,b',[(1,2),(3,4),(5,6)])#('变量名'，[1,2,3])
    def test_login01(self,a,b):
        print('-----test_login01---')
        assert a + 1==b #断言
        
    
    
```





