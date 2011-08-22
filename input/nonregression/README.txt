This repository will serve to host the dataset used in the regression testing
for OpenJPEG a JPEG 2000 implementation in C (BSD license)
http://openjpeg.org

Info:
- Marrin.jp2
- text_GBR.jp2
Those files were found from bug report #69 in openjpeg

---

Some files had been uploaded to opegjpeg google group. However those files were deleted due to google change in policy:

...
Zipped versions of the pages and files associated with this group will be available for download until August 31, 2011. After this date, this feature and the zip file downloads will be turned off permanently.
...

Those files have been uploaded as:
- 123.j2c
- MarkerIsNotCompliant.j2k
- _00042.j2k
- bug.j2c
- buxI.j2k
- buxR.j2k
- cthead1.j2k
- file2.jp2
- file9.jp2
- merged.jp2
- movie_00000.j2k
- movie_00001.j2k
- movie_00002.j2k
- orb-blue10.lin.j2k
- orb-blue10.lin.jp2
- orb-blue10.win.j2k
- orb-blue10.win.jp2
- test_lossless.j2k


Some files were added from debian bug tracker:
http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=413033
- broken*

-----

Another file was added from:
http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=617818
- http://www.fnordware.com/j2k/relax.jp2

-----

The now famous: CT_Phillips_JPEG2K_Decompr_Problem.j2k is the original image that started it all
At the time when there was only one reference JPEG 2000 library (JasPer), this image suddenly appear and
discover an error in the JasPer code. The bug has never been fixed in JasPer since its initial report (~2005).
In the meantime the guys from OpenJPEG quickly fixed it and thus openjpeg was adopted in GDCM and jasper removed.

-----

Adding an image with multiple tiles:
- Bretagne2.j2k

-----
Adding a subdirectory: J2KP4files which contains the JP2 and J2K (only) files from :
wget http://www.crc.ricoh.com/~gormish/jpeg2000conformance/j2kp4files_v1_5.zip
-----

illegalcolortransform.j2k is a special file. This used to be known as:
http://gdcm.sourceforge.net/thingies/jp2c.j2k

This file contains a value of 0x01 at offset 0x36, while it should be 0x00. kakadu gracefully
handles it with a message:
Illegal colour transform specified when image has insufficient or incompatible colour components.
OpenJPEG simply segfaults (1.4)
