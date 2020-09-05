# get-data-from-database
this is demo


```php

	function GetCurrentWeekdata(){
		
		$query = $this->db->query("select COUNT('id') as total from user WHERE YEARWEEK(`created_at`, 1) = YEARWEEK( CURDATE() - INTERVAL 0 WEEK, 1) AND user_type != 'admin-777' ");
		$re = $query->result();
		return $re[0]->total;
		
	}
	
	function GetCurrentMonthdata(){
		 
		$query = $this->db->query("select COUNT('id') as total from user WHERE MONTH(`created_at`) = MONTH(NOW()) AND user_type != 'admin-777'  ");
		$re = $query->result();
		return $re[0]->total;
		
	}
	
	
	function GetCurrentQuadata(){
		
		$query = $this->db->query("select COUNT('id') as total from user WHERE `created_at` >= DATE(NOW()) - INTERVAL 3 MONTH AND user_type != 'admin-777'  ");
		$re = $query->result();
		return $re[0]->total;
		
	}
	
	
	function GetCurrentyeardata(){
		
		$query = $this->db->query("select COUNT('id') as total from user WHERE  YEAR(`created_at`) = YEAR(DATE_SUB(CURDATE(), INTERVAL 0 YEAR)) AND user_type != 'admin-777' ");
		$re = $query->result();
		return $re[0]->total;
		 
	}

```
