MQTcPdf 0.0.2-dev:
========================

ZF2 module for TcPdf

Release Notes
========================

0.0.2-dev:

- Forked QuTcPdf
- Renamed the repo to MQTcPdf
- Updated composer file with new package info
- Updated TcPdf to version 6.0.23

0.0.1-dev:

- Initiation TcPdf in zf2

Installation
========================

Add this repository to your composer.json file:

```
"repositories": [
	{
		"type": "vcs",
		"url": "https://github.com/milqmedia/MQTcPdf"
	}
]
```

And ```"milqmedia/mq-tcpdf": "dev-master"``` to the require list or use the command line:

```
cd YourFolderProject/
php composer.phar require "milqmedia/mq-tcpdf":"dev-master"
```

Integration
========================
```php
  $sm  = $this->getServiceLocator();
  $pdf = $sm->get('MQTcPdf');
  $pdf = $pdf->MyPdf();

  $pdf->setHeaderData($ln = 0,$lw = 0,$ht = 0,$hs = 0,$tc = array(255,255,255),$lc = array(255,255,255));
  $pdf->setFooterData($tc = array(255,255,255),$lc = array(255,255,255));
  $pdf->setPageOrientation($orientation='P', $autopagebreak='L', $bottommargin=-200);

  foreach($pages as $page){

    $pdf->AddPage();

    //Your function
    $this->multiPag($pdf,$page);

    $pdf->lastPage();

  }

  $pdf->Output('test.pdf','I');
```

References usage and conditions in TcPdf
========================
- View read me in MQTcPdf/src/TcPdf
