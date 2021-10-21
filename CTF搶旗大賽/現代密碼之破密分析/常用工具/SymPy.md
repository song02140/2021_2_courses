## [sympy](https://www.sympy.org/en/index.html)
- symbolic calculation(符號運算) in python
- SymPy是一個符號計算的Python庫。
- 它的目標是成為一個全功能的計算機代數系統，同時保持代碼簡潔、易於理解和擴展。
- 它完全由Python寫成，不依賴於外部庫。 
- SymPy支持符號計算、高精度計算、模式匹配、繪圖、解方程、微積分、組合數學、離散數學、幾何學、概率與統計、物理學等方面的功能


## Google Colab的環境建置
```
!pip install sympy
```



## 範例練習1:非常重要的 mod inverse計算

```
from sympy import mod_inverse
mod_inverse(11, 35) # returns 16  ==> 11*16 mod 35 =1
```

## 範例練習2:微積分

### 不定積分
```
import math
from sympy import *                                                                                              
x = symbols('x')
integrate(exp(2*x), x)
```
## 定積分
```
import math
from sympy import *                                                                                              
x = symbols('x')
integrate(exp(2*x), (x, 0, 1))
```

## 複雜的積分
```python
from sympy import init_printing, integrate, log, sqrt, symbols
init_printing()

x = symbols('x')
g = sqrt(x + log(x))
f = (x ** 2 + 2 * x + 1 + (3 * x + 1) * g) / (x * g * (x + g))
f
```

## 解工程數學的 常微分方程式(ODE: Ordinary Differential Equation)
```python
from sympy import *                                                                                       
t = symbols('t')

y = Function('y')
dsolve(Eq(Derivative(y(t), t) -3*y(t), 2), y(t))
```
## 參考資料

- [清華大學Programming Basics and Math Python](http://web.ntnu.edu.tw/~tsungwu/Python_DevOps/Part1_Basics&Math/section5_integration.html)
- [Markdown Cheat Sheet](https://zh.wikipedia.org/wiki/SymPy)
- [Python 符號運算套件：SymPy](http://keejko.blogspot.com/2018/11/python-sympy.html)
- [SymPy: Symbolic Computation in Python](https://towardsdatascience.com/sympy-symbolic-computation-in-python-f05f1413adb8)


## 在colab寫出漂漂亮亮的數學公式

https://colab.research.google.com/notebooks/markdown_guide.ipynb

- [tudev/Workshops-2020-2021](https://github.com/tudev/Workshops-2020-2021)
- [Learn How to Write Markdown & LaTeX in The Jupyter Notebook](https://towardsdatascience.com/write-markdown-latex-in-the-jupyter-notebook-10985edb91fd)
- [markdown cheat-sheet](https://www.markdownguide.org/cheat-sheet/)
- [Google Colab-使用LaTeX和Markdown](https://www.youtube.com/watch?v=wsXG_2W84ck)
