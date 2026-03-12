---
publish: true
comments: true
created: 2026-03-12T06:31:54.203+05:30
modified: 2026-03-12T06:44:13.623+05:30
cssclasses: ""
---

# Important!!!!! might come for midsem 
## Design A Microcomputer Based System to sense 8 analog input signals and produce 8 analog outputs. The inputs come from sensors that produce useful signals with a bandwidth of 1k Hz but are known to pick up higher frequency noise these signals are to be measured, to an accuracy of at least 1%. The output signals are to drive actuators with a maximum operating bandwidth of 100 Hz but which are affected by higher frequency signals. The actuators require signals to an accuracy of at least 1%. Draw the suitable block diagram for the above case.



# solution

![[Assets/WhatsApp Image 2026-02-16 at 12.25.22 PM.jpeg|640]]

![[Assets/WhatsApp Image 2026-02-16 at 12.27.13 PM.jpeg|640]]

As the sensors have a useful signal bandwidth of 1Khz the converter will need to sample each channel with a sampling rate of at least twice the frequency. ( 2kHz ) however the presence of high  frequency noise necessitates the use of anti aliasing filters to remove the noise. Assuming that a slight attenuation near 1 kHz is acceptable, it would be appropriate to use low pass filters with a cutoff frequency of 1 kHz. 6th order butterworthfilters would be a typical choice. as these are not ideal filters it is necessary to sample somewhat above the nyquist rate. an increase of 20% gives a sampling rate of 2.4kHz. if each channel is sampled at this rate, the ADC must be capable to sample 8 $\times$ 2.4 khz =  19.2kHz which corresponds to a conversion time of 52 microseconds. in order to acheive and accuracy of 1% 7bit resolution is required. Infact most general purpose ADCs and DACs have a resolution of at least 8 bits. so it would be sensible to use such devices for the input and output  the eight output channels are obtained from a single DAC using a series of sample and hold gates, which are individually controlled by lines from the processor , the outputs from the sample and hold gates would have step changes of voltage  as the outputs  were updated. as with the input filters, this reconstruction filters would typically be 6th order ButterWorth filter with a cutoff frequency of 100 Hz.
