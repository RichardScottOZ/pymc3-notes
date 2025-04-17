# %conda install m2w64-toolchain --yes
- windows reachable compiler toolchain g++


## numpy
- need python 3.10
- need numpy 1.19 or less by the looks then

C:\Users\rscott\AppData\Local\miniconda3\envs\risked\lib\site-packages\theano\scalar\basic.py:2412: FutureWarning: In the future `np.bool` will be defined as the corresponding NumPy scalar.
  self.ctor = getattr(np, o_type.dtype)
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
Cell In[1], line 1
----> 1 import pymc3 as pm
      2 import numpy as np

File ~\AppData\Local\miniconda3\envs\risked\lib\site-packages\pymc3\__init__.py:23
     20 import platform
     22 import semver
---> 23 import theano
     25 _log = logging.getLogger("pymc3")
     27 if not logging.root.handlers:

File ~\AppData\Local\miniconda3\envs\risked\lib\site-packages\theano\__init__.py:83
     75 # This is the api version for ops that generate C code.  External ops
     76 # might need manual changes if this number goes up.  An undefined
     77 # __api_version__ can be understood to mean api version 0.
     78 #
     79 # This number is not tied to the release version and should change
     80 # very rarely.
     81 __api_version__ = 1
---> 83 from theano import scalar, tensor
     84 from theano.compile import (
     85     In,
     86     Mode,
   (...)
     93     shared,
     94 )
     95 from theano.compile.function import function, function_dump

File ~\AppData\Local\miniconda3\envs\risked\lib\site-packages\theano\scalar\__init__.py:1
----> 1 from .basic import *
      2 from .basic_scipy import *

File ~\AppData\Local\miniconda3\envs\risked\lib\site-packages\theano\scalar\basic.py:2460
   2456         else:
   2457             return s
-> 2460 convert_to_bool = Cast(bool, name="convert_to_bool")
   2461 convert_to_int8 = Cast(int8, name="convert_to_int8")
   2462 convert_to_int16 = Cast(int16, name="convert_to_int16")

File ~\AppData\Local\miniconda3\envs\risked\lib\site-packages\theano\scalar\basic.py:2412, in Cast.__init__(self, o_type, name)
   2410 super().__init__(specific_out(o_type), name=name)
   2411 self.o_type = o_type
-> 2412 self.ctor = getattr(np, o_type.dtype)

File ~\AppData\Local\miniconda3\envs\risked\lib\site-packages\numpy\__init__.py:324, in __getattr__(attr)
    319     warnings.warn(
    320         f"In the future `np.{attr}` will be defined as the "
    321         "corresponding NumPy scalar.", FutureWarning, stacklevel=2)
    323 if attr in __former_attrs__:
--> 324     raise AttributeError(__former_attrs__[attr])
    326 if attr == 'testing':
    327     import numpy.testing as testing

AttributeError: module 'numpy' has no attribute 'bool'.
`np.bool` was a deprecated alias for the builtin `bool`. To avoid this error in existing code, use `bool` by itself. Doing this will not modify any behavior and is safe. If you specifically wanted the numpy scalar type, use `np.bool_` here.
The aliases was originally deprecated in NumPy 1.20; for more details and guidance see the original release note at:
    https://numpy.org/devdocs/release/1.20.0-notes.html#deprecations