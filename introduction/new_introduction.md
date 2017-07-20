# Technical introduction
_This section is in construction_ 

## How medical ultrasound works ?

This imaging technique is based on the propagation of ultrasound in the human body in order to realize medical diagnosis. Ultrasound is sound waves at a frequency that is too high to be perceived by the human ear. It behaves as the traditional sound and it propagates a little bit like waves in the sea. 

<figure>
  <img src="./acoustic_imaging_src/Fetal_Ultrasound.png" alt="" />
  <figcaption> Figure 1: fetal ultrasound
  
  Image source: https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/Fetal_Ultrasound.png/800px-Fetal_Ultrasound.png</figcaption>
</figure>

### Using the pulse echo sequence for ranging objects 

To localize objects we use the pulse echo concept. Remember last time you yelled in a valley ? Your voice bounced on the mountains and came back to your ear after some delay. To know how far is a cliff in front of you for example the idea is to measure the time your cry takes to come back to your years. Knowing the  sound speed c in air you can easily retrieve the distance d as it is half the delay t times the sound speed. The half factor count for the fact that our cry traveled a two way trip. A lot of animals use this principle to perform echolocation as bats or dolphins allowing them to "see with their ears". 

<figure>
  <img src="./acoustic_imaging_src/image/Echo_cliff.jpg" alt="" />
  <figcaption> Figure 2: Reflection of sound on a cliff
  
  Image source: http://www.larousse.fr/encyclopedie/divers/%C3%A9cho/45456</figcaption>
</figure>

### Both an emitter and a receiver: the transducer

In the case of medical ultrasound, ultrasounds are emitted and received by a unique device called a transducer. This latter is made of a special material subject to a phenomenon called piezoelectricity. When a mechanical stress is applied to such a material, it reacts by accumulating electric charges. As sound is nothing else than a mechanical vibration, the sound arriving on the transducer implies a mechanical stress which is converted in a electrical tension that can be measured. The contrary is also possible. A voltage applied to the transducer will lead to a mechanical stress which will propagate as ultrasound waves through the medium we want to investigate. For simplicity a transducer is a speaker and a microphone at the same time but it emits and detects ultrasounds.

<figure>
  <img src="./acoustic_imaging_src/Piezoelectric-Effect.jpg" alt="" />
  <figcaption> Figure 3: the piezoelectric effetc
  
  Image source: http://www.tech-faq.com/piezoelectric-effect.html</figcaption>
</figure>


### Reflections: a matter of acoustical impedance 
Unlike echolocation that aims to locate objects from reflection on their surface, medical ultrasound aims to produce an image of a medium by making ultrasounds penetrating it. Our body is made of bones, liquids, tissues... offering a complex geometry for our waves. To understand how waves are reflected in this complex medium, we first have to understand how a wave is reflected at an ideally flat interface of different material.

At the interface between two mediums, any incident wave splits in a transmitted and a reflected wave. The ratio of the transmitted wave and the reflected is related to the difference of impedance betwenn those two mediums. The acoustic impedance $$Z$$ of a medium is given by the formula $$Z=\rho{c}$$ where $$\rho$$ is the density and $$c$$ is the sound speed. The ration $$r$$ between the amplitudes of the reflected and incident waves is given by: 

$$r=\frac{Z_2\cos(\theta_i)-Z_1\cos(\theta_t)}{Z_2\cos(\theta_i)+Z_1\cos(\theta_t)}$$

So the more the acoustical impedances of the two mediums are different, the more the wave is reflected. For example the interface between air and water is really reflective as the density of water is much superior as the one of air (while the speed of sound is five times faster in water than in the air). This explains why a gel must be applied between the probe and the body : any left air would prevent ultrasound to penetrate our skin.

<figure>
  <img src="./acoustic_imaging_src/image/300px-Reflectionrefraction.jpg" alt="" />
  <figcaption> Figure 4: Reflection at an interface
  
  Image source: https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/Reflectionrefraction.jpg/300px-Reflectionrefraction.jpg</figcaption>
</figure>

### Ultrasound imaging: a reflectivity map

Most parts of our bodies are mainly composed of water, so the acoustic impedance of our different tissues don't variate so much around the value of the one of water. As the differences of impedance are low, the body is not so reflective for ultrasounds (except for the bones). If we send ultrasounds it will be mainly transmitted and at each depth a small partially reflected wave will propagate back. The more the variation of the local acoustic impedance is important, the more the wave is reflected. This leads us to what is an ultrasound image, it is a map of the reflectivity to ultrasound. So this modality of imagery shows the interfaces. It's quite natural for our brain to think to objects by their edges so almost no further processing is needed to interpret this image.



<figure>
  <img src="./acoustic_imaging_src/image/echolocation.jpg" alt="" />
  <figcaption> Figure 5: echolocation in the human body</figcaption>
</figure>




At time t0, some ultrasounds are emitted by the transducer which is located in the probe. A part of them is reflected at the first interface between the organ and the other tissues, then propagates back and is detected by the transducer at time t1. Another part of the ultrasounds is refclected on the second interface and is detected at time t2. The position of those interfaces can be calculated knowing the sound speed in the human body.



<figure>
  <img src="./acoustic_imaging_src/image/echolocation_graph.jpg" alt="" />
</figure>



### Assessing the origin of reflections by focusing

The delay between pulse and echo allows us to range the depth of the reflections occurring along the path of the ultrasonic pulse. But to form a proper 2D image we also need to know which direction those reflections come from. A solution to solve that problem is to focus the waves we send so that they travel along a line instead of propagating in every direction. It's the same idea than putting your hand around your mouth to direct your voice to somebody. By using acoustical lenses (that behaves the same as a classical magnifying glass but for sound) or by shaping the transducer in a parabolic way we can form a narrow beam along the which our pulse will propagate. This done, we know that the echoes we will receive will come from reflections along that line.

This improvement allows us to probe our medium line by line. An entire area has to be scanned to form an image. A way to do that is to rotate the transducer. The transducer is placed fully at left for example. A first pulse is emitted, echoes are recorded. Then the transducer is rotated just a bit and another pulse echo sequence is achieved. We repeat this process until the area of interest is swept. More modern approaches use several transducers to achieve both synthetic focusing and fast scanning with improved resolution but they are out of reach for this introduction. 

## Our solution: be simple, be low cost

We could keep talking about ultrasound imaging for hours as this technology has been under heavy development since decades. But we will stop here for the theory and go straight to the minimal hardware required to achieve an ultrasound image. More will be explained when needed. 

### A unique rotating transducer

Our solution to tackle the imaging processed is based on the first generations of scanners because of their simplicity. Those scanners contained only one rotating transducer. To gain versatility, probes were usually embedding several transducers as a unique transducer design couldn't fit all imaging purposes.

### The minimal data acquisition system

Data acquisition is the process of sampling signals that measure real world physical conditions and converting the resulting samples into digital numeric values that can be manipulated by a computer. It is done thanks to a data acquisition system. At echOpen, we try to use as few components as possible in that system in order to reduce the cost of our probe. Let's follow the signal in that system:
* First the transducer is put on the right position thanks to a motor.
* A circuit called a pulser is used to excite the transducer that behaves like a speaker. 
* The transducer is switched onto a listening mode (it behaves like a microphone). 
* The signal is amplified. This step is necessary to digitalize the signal, otherwise its amplitude would be too low.
* The signal is digitalized.
* Some processing is achieved to extract the relevant information we want to display. This is called envelope extraction. Some denoising can be applied at this step. 
* The collected lines are sent to the smartphone via wifi. 
* The scan conversion is achieved. This last step consists in rendering a conical image from the different recorded lines. 

Here is a simplified flowchart of the full device and a litlle more information about each component:

```mermaid
graph TD;

p[pulser]
s{switch}
t[transducer]
m((medium))
a[variable gain amplifier]
d[digitalization]
e[envelope detection]
c[scan conversion]
l[display]

subgraph device
a-->d
d-->e

p--high voltage <br/> emission-->s
s--low voltage <br/> reception-->a
s---t  
end

subgraph smartphone 
c-->l
end

e-.wifi.->c
t-.ultrasound <br/> propagation.->m
```

#### The pulser

The pulser is an electronic board that converts a logic signal that ranges from 0-3.3V into an analog one that ranges from -100V to 0V. That high voltage analog signal is needed to allow the transducer to emit ultrasounds.

#### The transducer and the switch
The transducer converts an electrical signal into ultrasounds thanks to the piezioelectric effect: an alternating current is applied across the piezoelectric crystal that grows and shrinks depending on the voltage applied. The alternating current makes the crystal vibrate quickly, which produces an ultrasound. After reflection, the sound hits the crystal and triggers the reverse piezoelectric effect. An electronic signal containing information about the reflections of the ultrasound waves is obtained.

#### The variable gain amplifier

In complex mediums such as the human body waves are attenuated. It means that their amplitude decreases all along their way. As a consequence, ultrasounds that were reflected deeper in the body arrive at the transducer with a lower amplitude and need to be amplified (remember that they also arrive later at the transducer). The variable gain amplifier is an electric component that amplifies the signals received by the transducer depending on their order of arrival. 

#### Digitalization
After the amplification, the signal is still analogical. It needs to be digitalized (converted into a logical signal) to be processed by other electronical components.

#### Envelope detection
The envelope detection is a procedure that is used to analyse the signal to detect the times at whitch reflected ultrasounds were received. It can be done with an analogical or a digital signal. We chose the latter option. For the moment this detection is realized thanks to the smartphone application, but our plan is to be able to do it inside the device. Indeed performing enveloppe detection in the smartphone recquires to send the complete signal by wifi to the smartphone, which we would like to avoid.

#### Scan conversion

The Scan Conversion allows one to recreate a clinical image from a set of data sent by a probe. The received image depends on the geometry of the probe. This process intends to recreate the 'real' image.


Using an ultrasound beamformer, we can scan an area line by line and gather data about each depth. Those data are collected and written in a chart. So each column contains data that have been collected for a particular direction, at different depths. If a color is attributed to each cell of the chart, a rectangular image is obtained. But as a column of the chart corresponds to a direction and not to a vertical line a distorded image is obtained. This means that a polar to cartesian scan conversion is necessary before display.

 A combined design scheme for polar to Cartesian scan conversion using nearest neighbor and linear interpolations has been implemented which optimizes both image quality and hardware requirement. The nearest neighbor interpolation is a simple method although it makes the image blocky. On the other hand, linear interpolation needs a few computations but is free from these artifacts in the far field. At the end of that process, we obtain a better representation of the reality.
 
 

<figure>
  <img src="./acoustic_imaging_src/image/scan_conversion_one.jpg" alt="" />
  <figcaption> Figure 6: Scheme of a scanned area</figcaption>
</figure>




<figure>
  <img src="./acoustic_imaging_src/image/scan_conversion_two.jpg" alt="" />
  <figcaption> Figure 7: Image obtained without polar to cartesian conversion</figcaption>
</figure>





After polar to cartesian scan conversion the object is displayed on the screen according to its real shape, which can be represented with clinical images such as :


![alt tag](http://wiki.echopen.org/images/7/7d/Image04.png)  
![alt tag](http://wiki.echopen.org/images/b/b8/Image03.png)

These two images are before/after scan conversion of an image of a liver



## Looking for further information ?

To learn more about the hardware of the latest version of the device, click [here](/stable/doc_hardware.md).

To learn more about the software, click [here](/stable/doc_software.md)

# List of authors
[Alister Trabattoni](https://github.com/halipster)
[Apolline Faidherbe](https://github.com/ApollineF)

