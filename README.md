
# kaggle-Home-Credit-Default-Risk

Authors：李林（3120220938）、杨洋（3220211141）、敬甲男（3220221052）、李翰杰（3120220936）  
Kaggle竞赛主页：https://www.kaggle.com/competitions/home-credit-default-risk  
github主页：https://github.com/leealim/kaggle-Home-Credit-Default-Risk

---

## 启动方法

1. 补充数据集  
    - 数据集存放路径：".\data\home-credit-default-risk\\~~~~~.csv"
2. pip install -r requriements.txt
3. 依次执行在vscode中的jupyter中执行：  
    - data-process-missing-value-handling.ipynb  
    - data-process-outlier-handling.ipynb  
    - feature-project-feature-increase.ipynb  
    - feature-project-choosing.ipynb  
    - model-fit-traditional-methods.ipynb()  
    - model-fit-deeplearning-methods.ipynb(可选。需要安装torch)  
    - 最终结果输出在result文件夹下(包括模型权重和TARGET列值)
4. 执行main.py获得后台集成了模型，图形化窗口界面(未完成)

可选，创建虚拟环境，执行setup_env.bat  
参考代码：

```CMD
@激活环境
cd .\hcdrvenv\Scripts\ 
.\activate
cd ..
cd ..

pip install -r requriements.txt

@关闭环境
cd .\hcdrvenv\Scripts\ 
.\deactivate
cd ..
cd ..
```

## 数据集描述

### 1. **application_{train|test}.csv**

这是主表，分为两个文件，分别用于训练（带有目标值）和测试（不带目标值）。
这也是所有应用的静态数据。在此数据样本中，一行表示一笔贷款。

### 2. **bureau.csv**

向征信局报告的其他金融机构提供的所有客户以前的信用额度（适用于在我们的样本中有贷款的客户）。
对于我们样本中的每笔贷款，行数与客户在申请日期之前在信用局拥有的信贷数量一样多。

### 3. **bureau_balance.csv**

信用局以前信用额度的每月余额。
该表有一行记录了向信用局报告的每个先前信用的历史记录。即该表有（在我们对先前信用有一些可观察的历史记录的月份的相对先前信用样本中的贷款）行。

### 4. **POS_CASH_balance.csv**

申请人在捷信拥有的以前的POS（销售点）和现金贷款的每月余额快照。
此表有一行，用于与我们样本中的贷款相关的捷信（消费信贷和现金贷款）中每个先前信贷（消费信贷和现金贷款）的每个先前信贷的每月历史记录。即该表具有（我们对之前的信用有一些可观察到的历史记录的月份的相关之前信用样本中的贷款）行。

### 5. **credit_card_balance.csv**

申请人以前在捷信中拥有的信用卡的每月余额快照。
此表有一行，用于捷信（消费信贷和现金贷款）中与样本中的贷款相关的每个先前信贷（消费信贷和现金贷款）的每个月的历史。即该表具有（我们对之前的信用有一些可观察到的历史记录的月份的相关之前信用样本中的贷款）行。

### 6. **previous_application.csv**

在我们的样本中有贷款的客户的所有先前的捷信贷款申请。
在我们的数据样本中，与贷款相关的每个先前申请都有一行。

### 7. **installments_payments.csv**

与我们样本中的贷款相关的先前在捷信中支付的信贷的还款历史。
a) 每笔付款都有一行加上 b) 错过的付款各有一行。
在我们的样本中，一行相当于一笔分期付款或一笔分期付款对应于与我们样本中的贷款相关的一笔先前捷信信贷的一笔付款。

### 8. **HomeCredit_columns_description.csv**

此文件包含各种数据文件中列的说明。

## 数据评价

通过提交对test集的预测结果submission.csv到kaggle可以获得ROC-curve分数
