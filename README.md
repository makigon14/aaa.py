# aaa.py
# -*- coding: utf-8 -*-
"""
Created on Sun Jul 22 00:32:08 2018

@author: makigon
"""


import numpy as np
import matplotlib.pyplot as plt

trainData=np.random.normal(0,1,(5,2))
trainData2=np.random.normal(-1,1,(5,2))
response=np.random.randint(0,2,(5,1))

red=trainData[response.ravel()==0]
plt.scatter(red[:,0],red[:,1],80,'r','^')

blue=trainData2[response.ravel()==1]
plt.scatter(blue[:,0],blue[:,1],80,'b','s')

newcomer=np.random.normal(0,1,(1,2))
plt.scatter(newcomer[:,0],newcomer[:,1],80,'g','o')


distance=pow(trainData[:,0]-newcomer[:,0],2)+pow(trainData[:,1]-newcomer[:,1],2)
distance=np.sort(distance)[::-1]

distance2=pow(trainData2[:,0]-newcomer[:,0],2)+pow(trainData2[:,1]-newcomer[:,1],2)
distance=np.sort(distance2)[::-1]

distance=distance[:,np.newaxis]
print(np.insert(distance,1,0,axis=1))






