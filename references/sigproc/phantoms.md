# Tissue mimicking phantoms

## Introduction
A tissue mimicking phantom is an object made of a material that is supposed to reproduce the acoustic properties of the human body. They
can be divided into two categories:
* those used by physicians to train themselves to perform certains exams,
* those used by engineers for image quality assesment. For the moment we at echOpen are a lot more interested by that second category.


## Commercially available tissue mimicking phantoms
As said before, there are two types of commercially available tissue mimicking phantoms. Here you can see an example of an ultrasound 
training model.

<figure>
  <img src="/references/sigproc/images/ultrasound_training_model.jpg" alt="" />
  <figcaption> Figure 1: ultrasound training model
  
  https://www.bluephantom.com/product/FAST-Exam-Real-Time-Ultrasound-Training-Model.aspx?cid=411</figcaption>
</figure>

But the phantoms we are interseted in are those that can be used for image quality assesment. Indeed, they can be used to measure certain
parameters such as:

* Spatial resolution. The spatial resolution can be measured by placing a series of two points that can be detected by the scanner close 
to each other, but at different distances from each other. Then you just have to take a look on the screen to see which points are still
distinguishable from their counterpart. You can also compare the values of the neighbouring pixels.

* Contrast resolution. There can be some areas in the phantom where the acoustic properties of the material are slightly different. You 
can estimate the value of contrast resolution by determining which of those areas you are able to distinguish on the screen. Contrast 
resolution is a key issue as it will strongly impact the device's capacity to detect tumors and cysts.

* Uniformity. Except for the areas and details dedicated to the resolution measurements, the material is supposed to be uniform in the 
object. So uniformity can be simply tested by evaluating the noise at different depths.

Phantoms can also be used to test the quality of the scan conversion algorithm. Easily detected objects are put on a horizontal line at
regular intervals. Then you just have to check if those objects are still detected on the same horizontal line. The same thing can be 
done with a vertical line.

Here you  can see an example of such a tissue mimicking phantom.

<figure>
  <img src="/references/sigproc/images/phantom.jpg" alt="" />
  <figcaption> Figure 2: tissue mimicking phantom for image quality assesment.
  
 http://www.cirsinc.com/products/all/67/multi-purpose-multi-tissue-ultrasound-phantom/ </figcaption>
</figure>

Those phantoms are reliable but they are expansive: they cost about $2000.


## Home-made tissue mimicking phantoms
A lot of recipes can be found on the internet to make home-made tissue mimicking phantoms. Most of the time they use agar or gelatin. The purpose is to obtain the same speed of sound and the same attenuation as those in human tissues. Results are often pretty good [1],[2].

However, those phantoms are mostly used as training models or for research experiments. I suppose it is due to the difficulty to "draw" precise shapes in the gel. The only example of feasible tissue mimicking phantom useful for image quality assesment I found is the one described in the article about the resolution integral: the Edinburgh pipe phantom[3]. As you can imagine they are useful to calculate the resolution integral but they cannot be used to determine resolution.

Nevertheless, I have an idea to try to make a home-made tissue-mimicking phantom that could be used for image quality assesment. When you put hot water and gelatin together you obtain a homogeneous fluid, that will turn into a gel when cooling. We could use a 3D-printed mold to "draw" the shapes we want to obtain. When removing the mold, there would be some kind of empty tubes in the gel. We could fill those tubes with another gel that has different acoustic properties. Another solution would be to put metallic or nylon wires in the gel.

If we make a home-made tissue mimicking phantom, we will have to test its properties. We will have to ensure that its acoustic properties are relevant and that the shapes are located in the right place.
Moreover, we would probably have to face experimental problems such as the difficulty to put a wire at a precise location in a gel (it is more difficult for the depth, indeed if your gel is translucide you can partly solve the problem by drawing a line at the bottom of the mould). There could also be air bubbles between the different gels, or the shapes could be unprecise etc ... Obtaining a good home-made phantom seems feasible but it would require a lot more time than buying one.

Here is a list of the stuff we would need:
- gelatin or agar or both
- water
- maybe we would need pure alcohol
- a heating mantle that is also a magnetic agitator
- a little bit of laboratory glassware
- rectangular plastic boxes (to put the gel in)
- an access to a 3D printer

## References
[1] _ Characterization and evaluation of tissue-mimicking gelatin phantoms for use with MRgFUS
[2] _ Measurement of Ultrasonic Properties of Fat Biological Phantom
[3] _ https://pdfs.semanticscholar.org/1eae/a3fcfd9eca87ebaccb5d6b605655f1f003b3.pdf
