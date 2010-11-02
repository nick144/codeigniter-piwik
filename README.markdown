CodeIgniter-Piwik
============

CodeIgniter Library for retrieving stats from Piwik Open Source Analytics.


Requirements
------------

1. CodeIgniter 1.7.2 - 2.0-dev
2. Piwik install 


Usage
-----
	
	// Set site specific piwik config vars in lib (this will be moved to a config file shortly)
	$this->piwik_url = 'http://stats.website.com';
    $this->token = '0b3b2sdgsd7e82385avdfgde44dsfgd5g';
    $this->site_id = 1;
	
	// Load Libary
	$this->load->library('piwik');

    // Get Actions
	// Get last 10 days
    $data['actions'] = $this->piwik->actions('day', 10);
	// Get last 6 months
	$data['actions'] = $this->piwik->actions('month', 6);

    // Get Last 10 Visitors
	$data['visitors'] = $this->piwik->last_visits();

    // Get Last 10 Visitors Formatted (tries to eliminate need from parsing whats returned from the last_visits function)
	$data['visitors'] = $this->piwik->last_visits_parsed();


To-do
-----

- Finish documentation for all library functions
- Move Piwik configuration variables to config/piwik.php
- Implement ability to enable/use geoip to retrieve city, region, and country from IP Addresses 