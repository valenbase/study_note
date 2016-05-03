#监督学习
***
>意在给出一种算法，需要部分数据集已经有正确答案。比如给定房价数据集，对于里面的每个数据，算法都知道对应的正确房价。
>对于监督学习中的每一个样本，都给出了明确的问题结果。如是肿瘤是恶性还是良性；每一个房屋的面子对应的房屋价格。

>监督问题也叫<b>回归regression</b>问题，回归问题是监督问题的一种，意指要预测一个连续的数据，比如房价。

><b>Classification 分类</b>
Discrete valued out(0 or 1)分类问题，要预测一个离散的输出值，有时候也会超过两个值

>回归问题的输入输出是连续的，分类的问题是离散的0 1 2 3的输出值


#无监督学习
***
>在无监督学习中，所使用的数据是没有区分的，没有属性标签。
给出某种数据，是否可以在数据中找出可能存在的结构。
无监督学习的方法会将数据分为不同的聚类，如会将监督学习中的数据分为良心和恶性，这就是聚类算法。
***

#Supervised Learning监督学习
>In supervised learning, we are given a data set and already know what our correct output should look like, having the idea that there is a relationship between the input and the output.

>Supervised learning problems are categorized into <b>"regression"回归 and "classification"分类</b> problems. In a regression problem, we are trying to predict results within a continuous output, meaning that we are trying to map input variables to some continuous function. In a classification problem, we are instead trying to predict results in a discrete output. In other words, we are trying to map input variables into discrete categories.


>Recall that in *regression problems*, we are taking input variables and trying to map the output onto a *continuous* expected result function.
>
>Linear regression with one variable is also known as "univariate linear regression."

>Univariate linear regression is used when you want to predict a single output value from a single input value. We're doing supervised learning here, so that means we already have an idea what the input/output cause and effect should be.
>
>The Hypothesis Function（假设函数），根据给定的输入值得出一组输出值
>
>Cost Function：We can measure the accuracy of our hypothesis function by using a cost function.power(h(x)-y)(误差的平方和)/(2*m)(m为计算的数目个数)

>Gradient Descent（梯度下降），So we have our hypothesis function and we have a way of measuring how accurate it is. Now what we need is a way to automatically improve our hypothesis function. That's where gradient descent comes in.
***
#Unsupervised Learning无监督学习
>Unsupervised learning, on the other hand, allows us to <b>approach problems with little or no idea what our results</b> should look like. We can derive structure from data where we don't necessarily know the effect of the variables.

>We can derive this structure by clustering the data based on relationships among the variables in the data.

>With unsupervised learning there is no feedback based on the prediction results, i.e., there is no teacher to correct you. It’s not just about clustering. For example, associative memory is unsupervised learning.
***


