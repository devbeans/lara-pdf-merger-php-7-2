# lara-pdf-merger

Taken from Rhyan Foo Kune's version with a minor fix in the switch statement where it's using continue instead of break statement<br/>

###Update

Fixed error in tcpdf.php line 17784
  
## Installation

### Laravel 5.x:

Require this package in your composer.json and update composer.

    "devbeans/lara-pdf-merger-php-7-2": "dev-master",

After updating composer, add the ServiceProvider to the providers array in config/app.php

    LynX39\LaraPdfMerger\PdfMergerServiceProvider::class,

You can optionally use the facade for shorter code. Add this to your facades:

    'PdfMerger' => LynX39\LaraPdfMerger\Facades\PdfMerger::class,
    
## Using

```php

$pdf = new LynX39\LaraPdfMerger\PdfManage;

$pdf->addPDF('samplepdfs/one.pdf', '1, 3, 4');
$pdf->addPDF('samplepdfs/two.pdf', '1-2');
$pdf->addPDF('samplepdfs/three.pdf', 'all');

//You can optionally specify a different orientation for each PDF
$pdf->addPDF('samplepdfs/one.pdf', '1, 3, 4', 'L');
$pdf->addPDF('samplepdfs/two.pdf', '1-2', 'P);

$pdf->merge('file', 'samplepdfs/TEST2.pdf', 'P');

// REPLACE 'file' WITH 'browser', 'download', 'string', or 'file' for output options
// Last parameter is for orientation (P for protrait, L for Landscape). 
// This will be used for every PDF that doesn't have an orientation specified
```
