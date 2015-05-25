#################################################################################
How to build Mobule for Platform
- It is only for modules are needed to using Android build system.
- Please check its own install information under its folder for other module.

[Step to build]
1. Get android open source.
    : version info - Android 5.0
    ( Download site : http://source.android.com )

2. Get SM-T535 open source code
    : SM-T535_EUR_LL_Opensource.zip, version : T535XXU1BOD8
    ( Download site : http://opensource.samsung.com )
      Unzip it, then you will see the file Platform.tar.gz which includes the platform source code.

3. Copy module that you want to build - to original android open source
   If same module exist in android open source, you should replace it. (no overwrite)
   
  # It is possible to build all modules at once.
  
4. You should add module name to 'PRODUCT_PACKAGES' in 'build\target\product\core.mk' as following case.
	case 1) e2fsprog : should add 'e2fsck' to PRODUCT_PACKAGES
	case 2) libexifa : should add 'libexifa' to PRODUCT_PACKAGES
	case 3) libjpega : should add 'libjpega' to PRODUCT_PACKAGES
	case 4) KeyUtils : should add 'libkeyutils' to PRODUCT_PACKAGES
	case 5) brctl : should add 'brctl' to PRODUCT_PACKAGES
	case 6) ebtables : should add 'ebtables' to PRODUCT_PACKAGES
	case 7) strongswan : should add 'charon', 'libcharon', 'libhydra', 'libstrongswan' to PRODUCT_PACKAGES

                  
ex.) [build\target\product\core.mk] - add all module name for case 1 ~ 8 at once
	PRODUCT_PACKAGES += \
    	libkeyutils \
    	libexifa \
    	libjpega \
    	e2fsck \
    	brctl \
    	ebtables \
    	charon \
    	libcharon \
    	libhydra \
    	libstrongswan 

5. excute build command
    make -j4

Note : 
 You can download the Sbrowser source code from the site below: http://opensource.samsung.com.
#################################################################################