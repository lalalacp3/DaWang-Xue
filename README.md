1. KDE  核密度图

plt.figure(figsize=(15,8))
ax = sns.kdeplot( )
sns.kdeplot(  )
plt.legend( )
plt.title( )
ax.set( )
plt.xlim()
plt.show()

2. barplot  条形图

sns.barplot('Pclass', 'Survived', data=train_df, color="darkturquoise")
plt.show()

3.heatmap 热力图

Selected_features = ['Age', 'TravelAlone', 'Pclass_1', 'Pclass_2', 'Embarked_C', 'Embarked_S', 'Sex_male', 'IsMinor']
X = final_train[Selected_features]
plt.subplots(figsize=(8, 5))
sns.heatmap(X.corr(), annot=True, cmap="RdYlGn")
plt.show()

