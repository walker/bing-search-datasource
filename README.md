#CakePHP Bing Search Datasource


##Installation

Put this datasource in app/models/datasources.

##Use

	$results = $bing->find('all', array('conditions'=>array('Query'=>'[search string]', 'Sources'=>array('News', 'Web'), 'News.Offset'=>'0')));