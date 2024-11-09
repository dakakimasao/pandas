# pandas
파이썬 판다스 과제 
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
#=========================우리쏘니!@#!@#====================================
sondata = pd.read_excel('stat.xlsx', sheet_name='son')
kimdata=pd.read_excel('stat.xlsx',sheet_name='kim')
kadata= pd.read_excel('stat.xlsx', sheet_name='kangin')

print(sondata)
print(kadata)
print(kimdata)

attapps = [sondata.iloc[0, 1], sondata.iloc[1, 1], sondata.iloc[2, 1]]
attplaytime = sondata['min'].iloc[0:3]

plt.title('attplaytime(min)')
labels = ['son', 'salah', 'vinicius']
attcolors = ['b', 'r', 'black']
plt.bar(labels, attplaytime, color=attcolors)
plt.ylabel('playtime (min)')
plt.show()

attcate = ['goals', 'assist', 'sp90m', 'xg']

sonattstat = sondata.iloc[0, 3:].values
salahattstat = sondata.iloc[1, 3:].values
viniattstat = sondata.iloc[2, 3:].values

num_vars = len(attcate)
label_loc = np.linspace(0, 2 * np.pi, num_vars, endpoint=False).tolist()

sonattstat = np.concatenate((sonattstat, [sonattstat[0]]))
salahattstat = np.concatenate((salahattstat, [salahattstat[0]]))
viniattstat = np.concatenate((viniattstat, [viniattstat[0]]))
label_loc += label_loc[:1]

plt.figure(figsize=(9, 9))
ax = plt.subplot(111, polar=True)

ax.plot(label_loc, sonattstat, label='son', linestyle='dashed', color='lightcoral')
ax.plot(label_loc, salahattstat, label='salah', linestyle='dashed', color='violet')
ax.plot(label_loc, viniattstat, label='vinicius', linestyle='dashed', color='skyblue')

ax.set_xticks(label_loc[:-1])
ax.set_xticklabels(attcate)
ax.legend()
plt.title('att atat')
plt.show()
#=========================강긩이======================================


mfapps = [kadata.iloc[0, 1], kadata.iloc[1, 1], kadata.iloc[2, 1]]
mfplaytime = kadata['min'].iloc[0:3]

plt.title('mfplaytime(min)')
labels = ['kangin', 'bellingham', 'bruno']
mfcolors = ['b', 'r', 'black']
plt.bar(labels, mfplaytime, color=mfcolors)
plt.ylabel('playtime (min)')
plt.show()

mfcate = ['goals', 'assist', 'kp90', 'xg']

kanginstat = kadata.iloc[0, 3:].values
balstat = kadata.iloc[1, 3:].values
brunostat = kadata.iloc[2, 3:].values

num_vars = len(mfcate)
label_loc = np.linspace(0, 2 * np.pi, num_vars, endpoint=False).tolist()

kanginstat = np.concatenate((kanginstat, [kanginstat[0]]))
balstat = np.concatenate((balstat, [balstat[0]]))
brunostat = np.concatenate((brunostat, [brunostat[0]]))
label_loc += label_loc[:1]

plt.figure(figsize=(9, 9))
ax = plt.subplot(111, polar=True)

ax.plot(label_loc, kanginstat, label='kangin', linestyle='dashed', color='lightcoral')
ax.plot(label_loc, balstat, label='bellingham', linestyle='dashed', color='violet')
ax.plot(label_loc, brunostat , label='bruno', linestyle='dashed', color='skyblue')

ax.set_xticks(label_loc[:-1])
ax.set_xticklabels(mfcate)
ax.legend()
plt.title('mf stat')
plt.show()
#===================================진민짜이!@#$!@#$!@#$================================

dfapps = [kimdata.iloc[0, 1], kimdata.iloc[1, 1], kimdata.iloc[2, 1]]
dfplaytime = kimdata['min'].iloc[0:3]

plt.title('dfplaytime(min)')
labels = ['kim', 'bandik', 'rudiger']
dfcolors = ['b', 'r', 'black']
plt.bar(labels, dfplaytime, color=dfcolors)
plt.ylabel('playtime (min)')
plt.show()

labels = ['kim', 'vandijk', 'rudiger']
tak= kimdata.iloc[0:3, 5]
inter = kimdata.iloc[0:3, 6]

plt.bar(labels, tak, label='tackleswon', color='b')
plt.bar(labels, inter, bottom=tak, label='interceptions', color='r')

plt.xlabel('dfstat')
plt.title('dffencivestat')
plt.legend()
plt.show()


