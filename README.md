# Results of the atomated potsherd detection
These folders store the results of the automated extraction of individual potsherd fragments in the soil surface provided by two different approaches. They both used the same orthophotomsaic. The original images were acquired by a DJI Phantom 4 Pro V2.0 flying at a height of around 3m above ground. These were acquired as part of the survey of the city of Abdera and its environments. These images correspond to plot 591.

Both folders contain shapefiles ready to be integrated into standard GIS software. References to the processes followed to create these files are:

Random Forest-based algorithm:
Orengo, H.A. and Garcia-Molsosa, A. 2019. A brave new world for archaeological survey: Automated machine learning-based potsherd detection using high-resolution drone imagery. Journal of Archaeological Science, 112: 105013.
https://www.sciencedirect.com/science/article/pii/S0305440319301001

Mask R-CNN algorithm:
Orengo, H.A.; Garcia-Molsosa, A.; Berganzo-Besga, I.; Landauer, J.; Aliende, P. and Tres-Martínez, S. In press. New developments in drone-based automated surface survey: towards a functional and effective survey system. Archaeological Prospection.


The orthophotomosaic can be downloaded from Google Earth Engine using the following code:

var orthomosaic = ee.Image('users/hao23/sherds/plot591');
Export.image.toDrive({
  image: orthomosaic,
  description: 'orthomosaic',
  maxPixels: 9e12,
  scale: orthomosaic.projection().nominalScale().getInfo(),
  region: orthomosaic
});
