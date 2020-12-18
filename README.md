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

