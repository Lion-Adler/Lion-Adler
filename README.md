- 👋 Hi, I’m @Lion-Adler
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Lion-Adler/Lion-Adler is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
#мОДЕЛЬ XOR

import numpy as np

import matplotlib.pyplot as plt

def act(x):
  return 0 if x <= 0 else 1

def go(C):
  x = np.array([C[0],C[1],1 ])
  w1 = [1,1,-1.5]
  w2 = [1,1,-0.5]
  w_hidden = np.array([w1,w2])
  w_out = np.array([-1,1,-0.5])

  sum = np.dot(w_hidden, x)
  out = [act(x) for x in sum]
  out.append(1)
  out = np.array(out)

  sum = np.dot(w_out,out)
  y = act(sum)
  return y

C1 = [(0.9,0.2), (0.6,1)]
C2 = [(0,0), (0,1)]


print( go(C1[0]),go(C1[1]))

print( go(C2[0]),go(C2[1]))
