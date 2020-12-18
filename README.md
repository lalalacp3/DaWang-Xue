# df_train 是下面所使用的范例
# 这只是有可能的流程，具体要按照给定的数据再进行调整
1. Import Data & Python Packages

首先导入工具，记得设置seaborn和matplotlib的画图样式
e.g.   plt.rc("font", size=14)
       sns.set(style="white") #white background style for seaborn plots
       sns.set(style="whitegrid", color_codes=True)


2. Data Quality & Missing Value Assessment (# 在训练集中的操作，之后要对test同样做这样的操作)

2.1.目标数据有多少个  print('number of samples is {}'.format(df_train.shape[0]))  #shape[0] 显示出行的个数，长度

2.2.处理Null值，看Null值的总数        df_train.isnull().sum()                                                                                # check missing values in train data

2.3.判断缺失值的所占百分比，如果缺失太多那么就舍弃，如果较少就继续下面的步骤

2.4.画直方图  ax=df_train['标签'].hist(里面的参数按照题目来设置)
            df_train['标签'].plot(参数按照题目来设置)
            ax.set(xlabel='标签')
            plt.xlim(参数 ,参数)
            plt.show()

2.5.根据所得到的结果，对于数据进行调整， 可以使用这个重新复制一份数据 train_data = train_df.copy()

2.6.作图对比原数据和调整后的树蕨
  plt.figure(figsize=(参数))
  ax = train_df["标签"].hist()
  train_df["标签"].plot()
  ax = train_data["标签"].hist()
  train_data["标签"].plot()
  ax.legend(['Raw 标签', 'Adjusted标签'])
  ax.set(xlabel='标签')
  plt.xlim(参数)
  plt.show()

2.7.如果变量之间看似有关系，要考虑多重共线性 (multicollinearity)
  e.g  train_data['TravelAlone']=np.where((train_data["SibSp"]+train_data["Parch"])>0, 0, 1)
       train_data.drop('SibSp', axis=1, inplace=True)
       train_data.drop('Parch', axis=1, inplace=True)
       （额外用一个变量表示关系）

2.8.# create categorical variables and drop some variables  （如有必要）
  e.g 
  training=pd.get_dummies(train_data, columns=["Pclass","Embarked","Sex"])
  training.drop('Sex_female', axis=1, inplace=True)
  training.drop('PassengerId', axis=1, inplace=True)
  training.drop('Name', axis=1, inplace=True)
  training.drop('Ticket', axis=1, inplace=True)

  final_train = training
  final_train.head()
  
3. Exploratory Data Analysis
  见EDA专题





















