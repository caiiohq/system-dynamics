from pylab import *

def rk4(s,h,d,x):#função runge kuta 4
    k1=h*d(x,s)
    k2=h*d(x+(h/2),s+(k1/2))
    k3=h*d(x+(h/2),s+(k2/2))
    k4=h*d(x+h,s+k3)
    yy= s+((k1+(2*k2)+(2*k3)+k4)/6)
    return yy

def deriv(t,s): 
    v = s[1]
    A = -k*s[0]/m-b*s[1]/m
    return array([v , A])

m=1
k=4.6
b=0.2
N=1000
time=100
h=(time)/N

v_0= 0
x_0= 10
y=zeros([N,2])
y[0]=([x_0, v_0])

t=zeros(N)
t[0]=0
stop=0

for j in range (N-1):
    t[j+1]=t[j]+h
    y[j+1]=rk4(y[j],h,deriv,t)
    

figure(1)
plot(t,y[:,0])
grid()
xlabel (' tempo (s)')
ylabel ('posição (m)')

dec=zeros(len(t))

for n in range(len(t)):
    dec[n]=x_0*exp(-0.5*b*t[n])

figure(2)

plot(t,y[:,0])
plot(t, dec, 'r.', ms=0.5)
plot(t, -dec, 'r.', ms=0.5)
grid()
xlabel(' tempo (s)')
ylabel('posição (m)')
show()

figure(3)
plot(y[:,0],y[:,1])#plotando velocidade por posição
grid()
xlabel( ' posição (m)')
ylabel('velocidade (m/s)')
show()
