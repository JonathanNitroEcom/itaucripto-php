# Itaucripto (PHP)

[![Latest Stable Version](http://poser.pugx.org/inicial/itaucripto-php/v)](https://packagist.org/packages/inicial/itaucripto-php) [![Total Downloads](http://poser.pugx.org/inicial/itaucripto-php/downloads)](https://packagist.org/packages/inicial/itaucripto-php) [![Latest Unstable Version](http://poser.pugx.org/inicial/itaucripto-php/v/unstable)](https://packagist.org/packages/inicial/itaucripto-php) [![License](http://poser.pugx.org/inicial/itaucripto-php/license)](https://packagist.org/packages/inicial/itaucripto-php) [![PHP Version Require](http://poser.pugx.org/inicial/itaucripto-php/require/php)](https://packagist.org/packages/inicial/itaucripto-php)

### Description

This class was created based on the Java version of Itaucripto.

### Composer

```shell
$ composer require inicial/itaucripto-php
```

### Usage

```php
<?php
require_once(dirname(__FILE__) . '/init.php');

$itaucripto = new \Itaucripto\Itaucripto();
$itaucripto->setCompanyCode('J0098765430001220000002598');
$itaucripto->setEncryptionKey('12ASDFG456KWE078');

$itaucripto->setOrderNumber(substr(time(),-8));
$itaucripto->setAmount('1,57');
$itaucripto->setDraweeName('Fabiano Couto');
$itaucripto->setDraweeDocTypeCode('01');
$itaucripto->setDraweeDocNumber('61022645099');
$itaucripto->setDraweeAddress('Av Presidente Vargas');
$itaucripto->setDraweeAddressDistrict('Centro');
$itaucripto->setDraweeAddressCity('Rio de Janeiro');
$itaucripto->setDraweeAddressState('RJ');
$itaucripto->setDraweeAddressZipCode('20070006');

// $itaucripto->setCallbackUrl('http://www.domain.com/callback');

$itaucripto->setBankSlipDueDate(date('dmY', strtotime('+7 day')));
$itaucripto->setBankSlipNoteLine1('Sr. Caixa,');
$itaucripto->setBankSlipNoteLine2('Não receber após o vencimento.');
$itaucripto->setBankSlipNoteLine3('Obrigado.');
$itaucripto->setNote('3'); // Needed to display the three lines on the bank slip

$data = $itaucripto->generateData();
?>
```

### Note

You can find more info about usage on class source code.

Report any bug or suggest changes using git [issues](https://github.com/inicialsolucoes/itaucripto-php/issues).
