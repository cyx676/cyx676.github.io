import math 
import numpy as np 
import matplotlib.pyplot as plt 
import mpl_toolkits.axisartist as axisartist #导入坐标轴加工模块
plt.rcParams['font.sans-serif']=['SimHei']
plt.rcParams['axes.unicode_minus']=False

fig=plt.figure(figsize=(6,4)) #新建画布
ax=axisartist.Subplot(fig,111) #使用axisartist.Subplot方法创建一个绘图区对象ax
fig.add_axes(ax) #将绘图区对象添加到画布中

def exponential_func(x, a=2): #定义指数函数
  y=math.pow(a, x)
  return y

X=np.linspace(-4, 4, 40) #构造自变量组
Y=[exponential_func(x) for x in X] #求函数值
ax.plot(X, Y) #绘制指数函数
def exponential_func(x, a=0.5): #定义指数函数
  y=math.pow(a, x)
  return y

X=np.linspace(-4, 4, 40) #构造自变量组
Y=[exponential_func(x) for x in X] #求函数值
ax.plot(X, Y) #绘制指数函数
ax.axis[:].set_visible(False)
ax.axis["x"]=ax.new_floating_axis(0, 0, axis_direction="bottom") #添加x轴
ax.axis["y"]=ax.new_floating_axis(1, 0, axis_direction="bottom") #添加y轴
ax.axis["x"]=ax.new_floating_axis(0, 0, axis_direction="bottom") #添加x轴
ax.axis["y"]=ax.new_floating_axis(1, 0, axis_direction="bottom") #添加y轴

ax.axis["x"].set_axisline_style("-|>", size=1.0) #给x坐标轴加箭头
ax.axis["y"].set_axisline_style("-|>", size=1.0) #给y坐标轴加箭头
ax.annotate(s='x', xy=(max(X), 0), xytext=(max(X)+0.5, 0.5)) #标注x轴
ax.annotate(s='y', xy=(0, 1.0), xytext=(-0.5, max(Y)+0.5)) #标注y轴

plt.show()
