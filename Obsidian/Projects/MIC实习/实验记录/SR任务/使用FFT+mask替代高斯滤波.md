在新的实验中，出于对可解释性的考虑，我们使用FFT代替高斯滤波，FFT之后使用MASK的方法区分低频和高频成分，然后逆傅立叶变换，用于替代高斯变换。
结果总体而言和替换前差不多，Lpips有微小下降，可以忽略![[SWD_FDIT_FFT.png]]