# Codeigniter-Symfony-EventDispatcher

Stand-alone library of Symfony EventDispatcher that can be used in any PHP framework or just pure PHP probject.

If you're looking simple one please visit:
https://github.com/shinbonlin/PHP-EventDispatcher

What's the different than original?

Nothing is changed except:

1. Remove **namespace** and **use**
2. Combine mutli files into one file.
3. ContainerAwareEventDispatcher.php and /DependencyInjection/RegisterListenersPass.php are not included.

Just made it can be easy used in **just 10 seconds** without installing by Composer.

## Symfony EventDispatcher

Original: https://github.com/symfony/EventDispatcher

## How to use

### Codeigniter 

1. Copy EventDispatcher.php and put it in **application/libraries** folder.
2. Create MY_Controller.php in **core** folder.
3. Edit MY_Controller.php

```
class MY_Controller extends CI_Controller
{


    public $event;

	public function __construct() {
        parent::__construct();

		$this->load->library('EventDispatcher');
		$this->event = new EventDispatcher();
    }
}
```

Register an Event

```
    $this->event->addListener('event_name', function () {
        echo 'Hello, World!';
    });
```

Run an Event

```
    $this->event->dispatch('event_name');
```

Result
```
Hello, World!
```

### Pure PHP

Example Code

```
$event = new EventDispatcher();

$event->addListener('event_name', function () {
    echo 'Hello, World!';
});

$event->dispatch('event_name');
```

Hope this helps.
