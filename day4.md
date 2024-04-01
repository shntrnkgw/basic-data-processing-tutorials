# Basic data processing tutorials Day 4: Get familiarized with NumPy and matplotlib

## Introduction to NumPy: Why not use lists?
We often have to deal with a series of values, rather than a single value. For example, the IR spectroscopy data would consist of two long series containing the wavenumber values and corresponding absorbance values. 

In Python (and in many other languages as well), series of values can be handled as a list. A list can be created like

```python
a = [0.0, 1.0, 2.0, 3.0]
```

But Python list is not convenient for calculation. For example, if you want to multiply a constant to every element in the list, you may want to do this:

```python
a = [0.0, 1.0, 2.0, 3.0]
b = 2.0*a # this will fail
```
But this will not work. Instead, if you do it in pure Python, 

```python
a = [0.0, 1.0, 2.0, 3.0]
b = [2.0*val for val in a] # this is OK
```
Although you may not understand how it works, you can feel that it is a bit tedious given the simplicity of the task. 

Instead, we can use array in NumPy. It's similar to Python list but supports many convenient operations. 

## 2. NumPy hands-on
Let's use NumPy. 

Create a new file, say, `test_numpy.py`, like we did in [Day 2](day2.md). 
In that file, paste the following code:

```python
#coding=utf-8

# import numpy but assign different name `np`
import numpy as np

if __name__ == "__main__":
    # make a numpy array from a list
    a = np.array([0.0, 1.0, 2.0, 3.0]) 
    print(a)
```

and run it. You see the printed array in the console. 
Numpy array can do many operations. Add the following lines to the script file and run it: 
```python
    # multiply constant
    print(a*2.0)
    # add constant
    print(a + 2.0)
    
    # another array with the same length
    b = np.array([4.0, 5.0, 6.0, 7.0])
    # add element-wise
    print(a + b)
    # multiply element-wise
    print(a*b)
```

See? This is handy. You can do much complicated operations. Add the following lines to your script file and run it:
```python
    # generate evenly spaced 100 values between 0 and 2*pi
    theta = np.linspace(0.0, 2.0*np.pi, 100)
    print(theta)

    # calculate sin of theta
    sintheta = np.sin(theta)
    print(sintheta)
```

This is just a very basic functionality of NumPy. You are highly encouraged to go through a tutorial (e.g., [NumPy quickstart](https://numpy.org/doc/stable/user/quickstart.html)). 

## 3. Matplotlib hands-on
Just looking at printed values is not fun at all.
Now let's learn how to visualize the data. 

I give you an already complete example. Create another file `test_mpl.py`, paste the code below, and give it a go. 

```python
# coding="utf-8"

import numpy as np
from matplotlib import pyplot

if __name__ == "__main__":
    # generate evenly spaced 100 values between 0 and 2*pi
    theta = np.linspace(0.0, 2.0*np.pi, 100)

    # calculate sin of theta
    sintheta = np.sin(theta)

    # plot
    pyplot.plot(theta, sintheta)

    # show the plotting canvas
    pyplot.show()
```

You will see a window popping up. 
Note that you should close the window to terminate the program. You can run another script only after terminating the current one. 

Like NumPy, matplotlib is a massive package and we cannot cover everything here. 
You are encouraged to go through a tutorial (e.g., [matplotlib quick start guide](https://matplotlib.org/stable/users/explain/quick_start.html#quick-start)). 
