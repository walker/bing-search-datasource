#CakePHP Bing Search Datasource


##Installation

Put this datasource in app/models/datasources.

##Use

	$results = $bing->find('all', array('conditions'=>array('Query'=>'[search string]', 'Sources'=>array('News', 'Web'), 'News.Offset'=>'0')));

Add your Bing developer credentials to the database.php file.

	public $bing = array(
		'datasource' => 'bing_search',
		'appId' => '[app id here]'
	);

Create a model to use the datasource with.

	class Bing extends AppModel
	{
		var $useDbConfig = 'bing'; // Set this to the DB config variable name you added to database.php
		var $name = 'Bing';
		var $useTable = false;
		
		// $validate is really defined in the __construct constructor because of i18n issues
		var $validate = array();
		
		/**
		 * Use $_schema to set any Bing fields that you want to use
		 * @var <type>
		 */
		public $_schema = array();
	
		function __construct($id = false, $table = null, $ds = null) {
			parent::__construct($id, $table, $ds);
		}
	}