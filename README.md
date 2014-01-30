#kohana-mobile-detect

Este módulo tem a finalidade de facilitar o uso do projeto **mobiledetect** com o framework kohanaphp.

**ATENÇÃO:** Não desenvolvi o mobiledetect, apenas o empacoteu em um módulo para kohanaphp com a finalidade de facilitar o uso.

## mobiledetect

The lightweight PHP class for detecting mobile devices (including tablets).

_version: Mobile-Detect-2.7.2_

[Oficial Page](http://mobiledetect.net/)

[Github Repository](https://github.com/serbanghita/Mobile-Detect/)

##Como usar


### 1 - Habilitar o modulo no bootstrap.php, por exemplo:

	...
	'mobile-detect' => MODPATH.'mobile-detect',
	...

###2 - Carregar a biblioteca:

	require Kohana::find_file('vendor', 'Mobile-Detect/Mobile_Detect');

###3 - Verifica se é um dispositivo móvel:

	 $mobile_detect = new Mobile_Detect;
 
     // Any mobile device (phones or tablets).
     if ( $mobile_detect->isMobile() ) {
        echo "Yes";
     }else{
     	echo "No";
     }
     
###Outras formas de verificação:

	// Include and instantiate the class.
	require Kohana::find_file('vendor', 'Mobile-Detect/Mobile_Detect');

	$detect = new Mobile_Detect;
 
	// Any mobile device (phones or tablets).
	if ( $detect->isMobile() ) {
	 
	}
	 
	// Any tablet device.
	if( $detect->isTablet() ){
	 
	}
 
	// Exclude tablets.
	if( $detect->isMobile() && !$detect->isTablet() ){
	 
	}
	 
	// Check for a specific platform with the help of the magic methods:
	if( $detect->isiOS() ){
	 
	}
 
	if( $detect->isAndroidOS() ){
	 
	}
	 
	// Alternative method is() for checking specific properties.
	// WARNING: this method is in BETA, some keyword properties will change in the future.
	$detect->is('Chrome')
	$detect->is('iOS')
	$detect->is('UC Browser')
	// [...]
	 
	// Batch mode using setUserAgent():
	$userAgents = array(
	'Mozilla/5.0 (Linux; Android 4.0.4; Desire HD Build/IMM76D) AppleWebKit/535.19 (KHTML, like Gecko) Chrome/18.0.1025.166 Mobile Safari/535.19',
	'BlackBerry7100i/4.1.0 Profile/MIDP-2.0 Configuration/CLDC-1.1 VendorID/103',
	// [...]
	);
	foreach($userAgents as $userAgent){
	 
	  $detect->setUserAgent($userAgent);
	  $isMobile = $detect->isMobile();
	  $isTablet = $detect->isTablet();
	  // Use the force however you want.
	 
	}
	 
	// Get the version() of components.
	// WARNING: this method is in BETA, some keyword properties will change in the future.
	$detect->version('iPad'); // 4.3 (float)
	$detect->version('iPhone') // 3.1 (float)
	$detect->version('Android'); // 2.1 (float)
	$detect->version('Opera Mini'); // 5.0 (float)
	// [...]

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/madeinnordeste/kohana-mobile-detect/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

