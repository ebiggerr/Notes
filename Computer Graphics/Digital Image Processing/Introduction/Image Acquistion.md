


# Image Sampling and Quantization
There are numeroues ways to acquire images, but the objective is the same: to generate digital images from sensed data. The output of most sensors is a continuos voltage waveform whose amplitude and spatial behaviour are related to the physical phenomenon being sensed. 

To create a digital image, we need to convert the continuos sensed data into a digital format. 

## Sampling 
An iamge may be continuos with respect to the x- and y- coordinates, and also in amplitude. To digitize it, we have to sample the function in both coordinates and also in amplitude. Digitizing the coordinate values is called ==sampling==. Digitizing the amplitude values is called [[#Quantization]].

![[Pasted image 20210705225614.png]]

The one-dimensional function in Figure `b` is a plot of amplitude (intensity level) values of the continuos image along the line segment AB in Figure `a`. The random variations are due to image noise. To sample this function, we take equallly spaced sample along line AB, as shows in Figure `c`. The samples are show as small dark squares superimposed on the function, and their (discrete) spatial locations are indicated by corresponding tick makes in the bottom of the figure. The set of dark squares constitute the `sampled` function. 

However, the values of the samples stilll span (vertically) a continuos range of intensity values.

## Quantization
In order to form a digital function the intensity values also must be converted (quantized) into discrete quantities. The vertical gray bar in Figure `c`  depicts the intensity scale divided ito eight discrete intervals, ranging from black to white. 

The vertical marks indicate the specific values assigned to each of the eight intensity intervals. 

The continuos intensity levels are quantized by assigning one of the eight values to each sample, depending on the vertical proximity of a sample to a vertical tick mark. The digital samples resulting from both ==sampling== and ==quantization== are shows as white square in Figure `d`.

