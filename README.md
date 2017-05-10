# config-params
Gettery pro zjištění v jakých módech je nette aplikace.

# instalace
```
composer require pikl-cz/config-params
```

# implementace v config.neon
```
extensions:
    - Pikl\DI\ConfigParamsExtension
```    
    
# použití
```
use Pikl\ConfigParams;

class BasePresenter extends Nette\Application\UI\Presenter {

	/** @var Pikl\ConfigParams */
	public $configParams;
	
	public function injectConfigParams(ConfigParams $configParams) {
        	$this->configParams = $configParams;
    	}

	function startup() {
		parent::startup();
		$this->template->debugMode = $this->configParams->getDebugMode();
	}

}
```
