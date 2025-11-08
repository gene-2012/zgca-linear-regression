# ZGCA 1102 - 线性回归教程作业

By Luo Jien

## 项目概述

本项目包含两个独立的线性回归分析案例，分别使用Spotify音乐数据集和学生表现数据集，展示了线性回归在不同领域的应用。项目涵盖了从数据预处理、特征选择到模型训练和评估的完整机器学习流程。

## 项目结构

```
├── spotify/
│   └── linear_regression_tutorial.ipynb  # Spotify数据分析
├── student_performance/
│   └── student_performance_prediction.ipynb  # 学生表现预测
├── ... # 一些未完成项目
└── README.md
```

## 1. Spotify音乐数据分析

### 数据集
使用Spotify音乐数据集，包含多种音频特征：
- loudness (响度)
- acousticness (声学性)
- danceability (舞蹈性)
- tempo (节拍)
- energy (能量) - 目标变量
- ...

### 方法论
#### 特征选择策略
- 应用SelectKBest进行特征重要性评估
- 通过皮尔逊相关系数分析特征与目标变量的关系

#### 模型实现
1. **简单线性回归 (SLR)**
   - 使用loudness作为单一特征预测energy
   - 分析特征与目标变量的线性关系

2. **多元线性回归 (MLR)**
   - 结合多个特征进行预测
   - 提升模型表现力

### 模型评估指标
- R² (决定系数) - 主要评估指标
- MSE (均方误差)
- RMSE (均方根误差)
- MAE (平均绝对误差)

### 验证方法
- K折交叉验证 (k=5)
- 训练集/测试集划分 (80/20)

## 2. 学生表现预测

### 数据集
学生表现数据集包含以下特征：
- Hours Studied (学习时间)
- Previous Scores (先前成绩)
- Extracurricular Activities (课外活动)
- Sleep Hours (睡眠时间)
- Sample Question Papers Practiced (练习试卷数量)
- Performance Index (表现指数) - 目标变量

### 方法论
#### 特征选择策略
- 使用SelectKBest进行特征重要性评估
- 选择与目标变量相关性最高的特征

#### 模型实现
1. **线性回归**
   - 基础线性回归模型

2. **K近邻回归 (KNN)**
   - 非参数回归方法
   - 捕捉局部模式

### 模型评估指标
- R² (决定系数)
- MSE (均方误差)
- RMSE (均方根误差)
- MAE (平均绝对误差)

### 关键发现
#### 特征重要性
- **Previous Scores** 与 Performance Index 之间存在强线性关系
- 其他特征也对预测结果有重要影响

#### 模型性能
当前最佳线性回归模型表现：
```
训练集 R²: 0.9876
测试集 R²: 0.9877
```

## 当前状态

- Spotify数据分析最佳 R²: **0.7871**
- 学生表现预测最佳 R²: **0.9877**

## TODO

- [ ] 修复损失函数显示部分的bug
- [ ] 尝试更多特征工程方法
- [ ] 探索其他机器学习算法
- [ ] 优化可视化效果

## 使用说明

1. 确保安装所需依赖包：
```bash
pip install pandas numpy scikit-learn matplotlib seaborn statsmodels
```

2. 运行Jupyter notebook：
```bash
# 进入相应目录运行
jupyter notebook spotify/linear_regression_tutorial.ipynb
# 或
jupyter notebook student_performance/student_performance_prediction.ipynb
```