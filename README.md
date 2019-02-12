# Lab-1
# Simple circuit 1
![circuit1](Thao_Lab1_ circuit1.png)  
#### Three sources of Unknowns:  
2 terminal passive devices: $R_1, R_2, R_3$ 3 of them  
voltages: $V_s, V_1, V_2, V_3$ 4 of them  
currents: $I_s, I_1, I_2, I_3$ 4 of them  
  
Given on the schematic: $R_1=68, R_2=47, R_3=10, V_s=2$  
Total of 11-4=8 unknowns
  
#### Three sources of Equations:  
passive devices: $V_1-R_1*I_1, V_2-R_2*I_2,V_3-R_3*I_3$ 3 equations  
meshes: $V_s-V_1, V_1-V_2, V_2-V_3$ 3 equations  
nodes: $I_s-I_1-I_2-I_3, I_1+I_2+I_3$ 2 equations



import numpy
from numpy import * 
set_printoptions(precision=5,linewidth=120,suppress=True)
import sympy 
from sympy import sqrt, symbols, Integral, pi, N, init_printing, pprint, linsolve
init_printing()

#solving for the currents I1,I2,I3,Is
V1, V2, V3, Vs, I1, I2, I3, Is = sympy.symbols('V1 V2 V3 Vs I1 I2 I3 Is')
R1=68
R2=47
R3=10
Vs=2
(sympy.solve([V1-R1*I1, V2-R2*I2,V3-R3*I3,Vs-V1, V1-V2, V2-V3,Is-I1-I2-I3], (V1,V2,V3,I1,I2,I3,Is), implicit=True))



# Simple circuit 2
![circuit2](Thao_Lab1_ circuit2.png)  
#### Three sources of Unknowns:  
2 terminal passive devices: $R_4, R_5, R_6$ 3 of them  
voltages: $V_s, V_4, V_5, V_6$ 4 of them  
currents: $I_s, I_4, I_5, I_6$ 4 of them  
  
Given on the schematic: $R_4=10000, R_5=20000, R_6=2200, V_s=2$  
Total of 11-4=8 unknowns
  
#### Three sources of Equations:  
passive devices: $V_4-R_4*I_4, V_5-R_5*I_5,V_6-R_6*I_6$ 3 equations  
voltage: $V_s-V_4-V_5-V_6$ 1 equations  
current: $I_s-I_4, I_4-I_5, I_5-I_6, I_s-\frac{V_s}{R_4+R_5+R_6}$ 4 equations  



#solving for the currents V4, V5, V6, Is
V4, V5, V6, Vs, I4, I5, I6, Is = sympy.symbols('V4 V5 V6 Vs I4 I5 I6 Is')
R4=10000
R5=20000
R6=2200
Vs=2
R=R4+R5+R6
I=Vs/R
(sympy.solve([V4-R4*I4, V5-R5*I5, V6-R6*I6, Vs-V4-V5-V6, Is-I4, I4-I5, I5-I6, Is-I], (V1,V2,V3,I1,I2,I3,Is), implicit=True))


