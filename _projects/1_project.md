---
layout: page
title: FIDS Open Research Lab
description: > 
  Artistic research boat equipped with various sensors and a high-resolution camera for automatic machine learning-based bird detection and tracking. Results are translated to sentences and displayed on a Flight Information Display System from an airport which is mounted to the back of the boat. 
img: assets/img/FIDS.jpg
importance: 1
category: work
related_publications: false
---



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FIDS.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/FIDS_technical.png" title="Technical drawing of the vessel." class="img-fluid rounded z-depth-1" %}
    </div>
</div>
## Technical Description

The fifteen-meter-long tow and tour boat, the Zoë X, serves as the basis for the FIDS Open Research Lab. In order to film the sky, a highly sensitive camera is mounted on the ship’s foredeck. In addition, there are numerous sensors that measure the data from the immediate surroundings, the environment, and the weather, such as the brightness of stray light (light pollution), acoustic pressure (noise), temperature, air pressure, wind speed and direction, and the location and direction of the ship.

Since the ship does not have enough solar energy to power the computing necessary to evaluate the visual data from the camera on board, it is wirelessly transmitted, along with the data from the sensors, to an external server at the project programmer’s home. There are four 4G/5G antenna set up on the roof of the Zoë X, creating the best possible network reception while out in the Hamburg harbor. In order to enable a fast rate of data transmission for the video stream, several mobile communications connections are bundled together.

Initially, the incoming video stream is pre-filtered with a sparse optical flow. This allows changes in pixels—from birds flying overhead, for instance—to be recognized and only the corresponding video sequences are used in the further analysis. This is performed by an artificial intelligence device that is trained to identify photos of birds. This way, the movements of birds in flight can be distinguished from clouds, airplanes, or insects passing over the camera lens.

Subsequently, multi-object tracking detects the flight paths of birds in the video sequences and similar flight paths are grouped into clusters. If a new bird comes into the picture, it is automatically determined if the bird belongs to an existing cluster, or flock of birds—or not. A fast Fourier transform algorithm with a sliding window is used to determine how frequently the wings beat. From the analysis of this data, disruptions to flightpaths, such as sudden or repeated changes in direction, can be inferred.

The automated evaluation of images and the additional sensory data are used as the foundation for generating text (with more than one billion different sentences possible). Using a formal language, the Natural Language Toolkit, various textual components are selected and combined to form (mostly) grammatically correct sentences. The result is transmitted from the server back to the ship, where it is displayed on a historical airport display board, which is mounted on the vessel’s stern.

These types of display boards, which usually show the arrivals and departures of airplane flights, are called “flight information display systems,” or FIDS for short. The board used here was installed at the Leipzig Halle Airport in 1993 and replaced by an LCD monitor thirteen years later. Separate hardware was developed to control it, because the electronics inside of it were no longer compatible with today’s computers. Due to its age, the board has display errors (permanent bright spots).

## Technical Data in Detail

### Ship:
type boat »Detzem« 14m, Siebert Berlin shipyard, built 1964. length over all 14.71 m, width over all 3.1 m, drawdown 0.8 m, height with superstructure and display board 3.15 m. Engine: Mercedes Benz MB 204-B, 4 cylinder, 12 l displacement, 99 HP.

### Camera:
Sony SNC-VB 770: 4K resolution, minimum illumination 0.004 lux (30 IRE)

### Sensors:
TinkerForge sensors are used.
- Wireless Weather Station WS-6147 (temperature (in C°), humidity (%RH), wind speed (m/s), wind direction, precipitation (mm))
- Ambient Light Bricklet 3.0 (0.01 lux to 64000 lux)
- sound pressure level (30 dB to 120 dB, 40 Hz to 40960 Hz)
- GPS Bricklet 2.0 (elevation, azimuth, and SNR for each GPS/GLONASS satellite)
- IMU Brick 2.0 (six degrees of freedom for each three-axis accelerometer, compass, gyroscope).

### Display board
AEG MIS D414 LCD segmented display with newly developed controls based on BeagleBone Black. Backlighting was upgraded to line-dimmable LED illumination (maximum 4000lm/m, effektiv 100W/h, maximum 1200 W/h).

### Power supply
A total of seventeen solar panels with a total output of 1850Wp are installed on the fore- and aft decks, as well as on the roof of the cabin and the wheelhouse, supplying a 7kW/h LiFePo4 bank of batteries.

### Cellular internet connection
Two ZTE 801A 5G routers with SIM cards from different providers, bundled via openMTCP into an APU.2E4 (network bundle).

### Server (on land)
CPU Intel Core i9 12900K, RAM 64GB DDR5, 2x GPU Nvidia 1080 Ti, power consumption nominally 1250 W/h max.

## Further Links
- [Project Website](https://fids-openresearchlab.org/)
- [Press Article on riffreporter](https://www.riffreporter.de/de/technik/voegel-bestimmen-mit-kuenstlicher-intelligenz-und-ueberwachungskamera
)
- [Press Article on szene-hamburg.com](https://szene-hamburg.com/blick-nach-obenbarkasse-kunst-hafen-voegel-claudius-schulze/#)
- [Press Article on taz](https://taz.de/Vollautomatische-Vogelbeobachtung/!5878304/)