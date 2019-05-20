# Soap Eprints Server

SOAP Web service interface for Eprints 3.x. http://www.eprints.org/uk/  and PHP client.

## Getting Started

Create directory soap in eprints3/cgi

1. cd `eprints_install/cgi`
2. mkdir `soap`
3. copy MetaDataServ.cgi  SearchServ.cgi putEprint.cgi to `eprints_install/cgi/soap`

### Prerequisites

```sudo apt-get install libsoap-lite-perl```


## How to use 

```php

$search = new EpClient();

/**
 * search data, return list id
 */

$search->fileds = array('title');
$search->key = 'Google';
$result_search = $search->search();

/**
 * get medatada by id item, return list metadata
 */
$search->ids = array('1');
$result_metadata = $search->getMetadata();

/**
 * put metadata
 */

echo "============= Input items result =========== ";
$search->title = 'Test soap client php 2';
$search->abstract = 'testing soap client php';
$search->creators_name = array(array('family' => 'test family1'), array('family' => 'test family2'));
$search->date = '2012-09-30';
$search->type = 'article';
$search->url_file = 'http://site/id/file.pdf';
$result_put = $search->put();

```


## Authors

* **Novytskiy Oleksandr**


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

