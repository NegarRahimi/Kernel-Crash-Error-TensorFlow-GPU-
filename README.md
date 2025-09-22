# Kernel-Crash-Error-TensorFlow-GPU-
Solution for TensorFlow GPU kernel crash on Windows (missing zlibwapi.dll)
**I'm sharing this in hopes of saving you some time—it took me a while to figure out the issue!
I was trying to run my Python code using TensorFlow with GPU support instead of CPU. After finding the correct versions of everything and making sure my code was running on the GPU, I ran a convolutional code, and the kernel crashed!
Here’s the solution that worked for me:
Go to the environment you created (C:\Users\krist\anaconda3\envs\ <Your env name> \Library\bin) and check whether a file named “zlibwapi.dll” exists in that directory.
In my case, the file was missing—and this was the reason the kernel crashed, even though the code was running on the GPU.
If you're missing zlibwapi.dll, you have two options:
1.	Try to find a safe version online and manually place it in the environment directory (though I couldn’t find a trustworthy source myself).
2.	Recommended: Create a working PyTorch environment, like what you did for TensorFlow, copy the “zlibwapi.dll” file from (C:\Users\krist\anaconda3\envs\ (<Your env name>) \Lib\site-packages\torch\lib\zlibwapi.dll), and paste it into your TensorFlow environment (C:\Users\krist\anaconda3\envs\ <Your env name> \Library\bin).

In case it helps:
I'm using a Windows laptop with an NVIDIA GeForce RTX 4050 GPU.
Here are the versions that worked for me:
•	TensorFlow: 2.10
•	CUDA: 11.8
•	Python: 3.10.18
You might be able to use more updated versions, but if those don’t work, this combination is a safe option.
**
