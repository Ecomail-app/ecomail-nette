Ecomail API for Nette
=====================

Easy implementation of Ecomail.app API

Requirements
------------
- Nette 2.3 or above

Instalation
------------

Install with `composer.json`:
```
	"require": {
		"haltuf/ecomail-nette": "dev-master"
	}
```

or

```
composer require haltuf/ecomail-nette:@dev
```

Usage
-----

Add following to `config.neon`:

```
extensions:
	ecomail: Ecomail\Extension

ecomail:
	key: YOUR_KEY_HERE
```

And inject service into Presenter:

```php
	/** @var \Ecomail\Ecomail @inject */
	public $ecomail;
```

Then you can use:

```php
	// get all lists
	$this->ecomail->getLists();

	// get list
	$this->ecomail->getList(1);

	// get subscribers with pagination (20)
	$this->ecomail->getSubscribers(1, $page);

	// get subscriber from list with ID 1
	$this->ecomail->getSubscriber(1, 'example@example.com');

	// create or update subscriber
	$this->ecomail->addSubscriber(1, array('email' => 'example@example.com', FALSE, TRUE, TRUE));

	// delete subscriber
	$this->ecomail->deleteSubscriber(1, 'example@example.com');
```
