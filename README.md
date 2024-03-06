# win10+4070ti+cuda+cudnn 安裝紀錄
1. cuda v11.2  https://developer.nvidia.com/cuda-toolkit-archive
2. cudnn v8.1.0
3. NV驅動 528.02
   
tensorflow-gpu<=2.4 

參考: https://medium.com/ching-i/win10-%E5%AE%89%E8%A3%9D-cuda-cudnn-%E6%95%99%E5%AD%B8-c617b3b76deb

# cuda v11.2出現錯誤

Tensorflow GPU Could not load dynamic library 'cusolver64_10.dll'; dlerror: cusolver64_10.dll not found

參考: https://stackoverflow.com/questions/65608713/tensorflow-gpu-could-not-load-dynamic-library-cusolver64-10-dll-dlerror-cuso
![image](https://github.com/CHIJUI0128/4070TI-CUDA/assets/56662495/c38fd850-6c4b-4b6d-ba46-1daca9d15e07)


# 測試
1. cuda

打開cmd =>  nvcc -V

2. cudnn

打開cmd 

=>  C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\vX.X\extras\demo_suite\bandwidthTest.exe

=>  C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\vX.X\extras\demo_suitedeviceQuery.exe

如果顯示 Result = PASS 安装成功。

3. gpu
   
import tensorflow as tf 

tf.test.is_gpu_available(cuda_only=True)
