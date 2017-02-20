# laravel-ip-access
IP restriction middleware for Laravel 5

# Usage

Add to your Kernel.php

```
protected $routeMiddleware = [
	'auth' => \Illuminate\Auth\Middleware\Authenticate::class,
	'auth.basic' => \Illuminate\Auth\Middleware\AuthenticateWithBasicAuth::class,
	'bindings' => \Illuminate\Routing\Middleware\SubstituteBindings::class,
	'can' => \Illuminate\Auth\Middleware\Authorize::class,
	'guest' => \App\Http\Middleware\RedirectIfAuthenticated::class,
	'throttle' => \Illuminate\Routing\Middleware\ThrottleRequests::class,
	
	// Add this line
	'ip' => \App\Http\Middleware\IpAccess::class,
];
```

And than, you can use like bellow.

```
Route::group(['prefix' => '/api', 'middleware' => ['ip:127.0.0.1,192.168.*']], function() {
	
	// Your ip restricted routes goes here!
	
});
```

You can use full ip address and ip groups like `192.168.*`

