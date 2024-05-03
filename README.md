# -The-model-of-height-and-weight-of-a-healthy-body
I made a function that shows The model of height and weight of a healthy body. 

Project-Python Implementation of Linear Regression Line

According to Body Mass Index (BMI) The average weights of healthy body for the corresponding heights are given in the following table:
Height in inches (h)
58
60
61
64
66
69
70
71
72
73
Average weight in pound (w)
102
109
113
125
133
146
149
153
158
162
source-:https://www.cancer.org/cancer/risk-prevention/diet-physical-activity/body-weight-and-cancer-risk/adult-bmi.html

def bestFitLine(x,y) : 
    N= len (x) 
    sx=0 # the sum of x values 
    sy=0 # the sum of y values 
    sxy=0 # The sum of product of corresponding x and y values 
    sx2=0 # The sum of squers of x values 
    for i in range(N):
        sx=sx+x[i]
        sy=sy+y [i]
        sxy=sxy+x[i]*y[i] 
        sx2=sx2+x[i]*x[i]
    m= (N*sxy-sx*sy) / (N*sx2-sx*sx) 
    b=(sy-m* sx)/N 
    return m,b  
    
