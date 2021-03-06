## python数据访问
### 基本I/O
1. open； with
2. 内置pickle模块
3. 内置open逐行读取文件
4. sqlite3模块访问SQLite3数据库
5. numpy第三方模块读取*.npy文件
### pandas模块
高效读写
### python数学工具
1. 凸优化
	全局优化brute，局部优化fmin
	使用scipy.optimize.brute scipy.optimize.fmin进行
	brute通过网格离散化求解全局最优
	有约束的凸优化：等式/不等式约束
2. 逼近
	（1）插值/回归
		插值复杂
		回归需要合适的函数
	（2）多项式拟合
		高次多项式在有限区间上强行过拟合非线性函数不可
		多项式不便拟合正弦函数
		先验选择基函数提高效率
	（3）更优方法
		numpy.linalg.lstsq基于最小均方差的拟合方法
		只要noise服从N（E=0），选用恰当基函数，最小二乘法就能得到最佳拟合
		
## 资金管理模型
### 意义
头寸、方向、时机
### 确定头寸规模的四种模型
1. 每一固定金额交易
2. 等价值交易单位
3. 百分比模型
4. 百分比波动幅度模型

#### 细节考虑：流动性风险
1. 持仓头寸不超过改股票流通市值的2%
2. 日成交量不超过该股票成交量的10%

#### 风险管理
1. CPR公式： P（头寸规模）=C（总风险）/R（每股风险）
2. 总风险可行取值：预警线0.9；清盘线0.85
3. 单个头寸的风险： 固定风险/波动利率
4. 单个头寸与总风险协调：设置最大持仓上限、日最大成交量，平均分配风险，但是可能会造成比较大的资金闲置
5. 财务报表：BS/IS/SE etc
6. 本福特定律： 数字出现的频率并不是均匀分布，以1开头的数字出现的频率可能高达30%
