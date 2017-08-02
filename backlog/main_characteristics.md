# Main characteristics

Here is a synthesis of the main constraints to be addressed by the device. These ones are deduced from the CapMed that took place on June 18th, 2016.

## Use of the device

The echOpen device is meant to be a universal ultra-portable ultrasound imaging or medical visualization tool, intended to accompany health professionals in clinical practice of diagnosis orientation. Echostethoscopy is primarily aimed to physicians who have never taken ultrasound images and who have taken a 48-hour training program to master the gesture and the concept.

The echOpen probe is an internal echo-anatomy visualization tool used in the clinical examination, enabling healthcare professionals to:

* See inside the body
* Find an organ, a vascular structure, ...
* Estimate its volume \(large, medium, small\) and its dynamics, without tissue analysis
* Supplement clinical semiology for diagnosis guidance for general practitioners and specialists

It is not :

* A complementary review tool
* A standalone imaging tool
* A tool for tissue analysis

For now, Doppler ultrasonography is out of the scope of the developments.

The device goes with an app which allows to display the images on a smartphone, control some device parameters, store and share screenshots or video sequences. Some sets of parameter settings have to be pre-defined, allowing the user to load some pre-determined settings depending on the patient's characteristics \(gender, height, weight...\) and the targeted organ.

## Image characteristics

* The echOpen device is meant to produce ultrasound images in B-mode, which is one of the different ultrasound modes used in medical imaging. In this mode, one obtains a cross-sectional image representing tissues and organ boundaries within the body. The brightness of the image at each point is related to the amplitude of the echo coming from that point, giving rise to the term B-mode \(brightness mode\). As ultrasounds are reflected at the interface between oragns and tissues, an image showing the shape of an organ can be obtained thanks to this technique. [Here](http://assets.cambridge.org/97805217/57102/excerpt/9780521757102_excerpt.pdf) is an article that you can read to get more information about B-mode imaging.

* For a real-time usage, the images are expected to be displayed with a minimal framerate of 10fps.

* The image quality must be compatible with the medical usage described above. For this reason, the expected resolution must be about 1mm at distances that are relevant for the examination of a patient. The detailed technical constrains related to image characteristics are listed in [Technical constrains](backlog/technical.md).

## Main technical requirements

* Three different frequencies \(3.5 MHz, 5MHz, 7.5MHz\) for different medical applications
* Mechanical probe: rotative or oscillating head with one piezo per frequency
* Ultra-portable: the whole device can be carried in a blouse pocket, limited weight
* Robust: the device should be resistant to a 50cm fall \(which approximately corresponds to the height of a bed\)
* Sufficient battery life: at least one hour of continuous use
* Waterproof and easy to clean
* Low-cost: affordable for a healthcare professional



## List of authors

[Aurélie](https://www.gitbook.com/book/echopen/echopen_prototyping/edit#)

