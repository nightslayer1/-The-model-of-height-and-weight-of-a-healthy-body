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

I used this function to help me find BestfitLine.
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


I used this function to find correlation coefficient
def corrCoefficient(x,y):
    N=len (x) 
    sx=0 # the sum of x values 
    sy=0 # the sum of y values
    sxy=0 # The sum of product of corresponding x and y values 
    sx2=0 # The sum of squers of x values
    sy2=0 # The sum of squers of y values 
    for i in range(N):
        sy=sy+y[i]
        sxy=sxy+x[i]*y[i] 
        sx2=sx2+x[i]*x[i]
        sy2=sy2+y[i]*y[i] 
        r=(N*sxy-sx*sy)/np. sqrt((N*sx2-sx*sx) * (N*sy2-sy*sy)) 
        return r

I also used this function to make the scatter plot.
# Create bubble vector 
bubb= []
for i in range(len(h)): 
    bubb. append(w[i]) 
    
# Draw the scatter plot 
plt.scatter(h,w,c="pink",marker="*",s=bubb) 
    
# Label of axis 
plt. xlabel ("Height of the body (h)") 
plt. ylabel ("Weight of the body (w)")
    
# Title the graph 
plt. title("Scatter plot and Graph of the Model") 
    
# Plot graph of the model
x=np. linspace (50,80,100)
y=[] 
for i in x: 
        y. append(i*bestFitLine(h,w)[0]+bestFitLine(h,w)[1]) 
plt. plot(x,y) 
        
# Write equation of model in the graph
plt. text (54,80, "w=4.024h-132.22")
# display the graph, Labels and title
plt. show()
