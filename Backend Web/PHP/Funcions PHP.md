# Funcions PHP
Podem fer funcions que retornen valors quan li pasem valors.

```PHP
<?php

	function suma($a, $b) {
		return $a + $b;
	}
	
	echo suma(5, 10);

?>
```

Podem fer funcions que no retornen valors quan li pasem valors.

```PHP
<?php

	function suma($a, $b) {
		echo $a + $b;
	}

?>
```

Podem fer funcions que no li pasem valors i retonen.

```PHP
<?php

	function suma() {
		return 2 + 2;
	}
	
	echo suma();

?>
```