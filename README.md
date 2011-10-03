PHP Stripe Library
==================

Recently I received an invitation for stripe.com, is a fantastic payment gateway/processor service.
Their main focus, as far as I can tell at least, is precisely developers and they have a pretty amazing API and
several languages bindigs.

The PHP binding however was a little bit too complex for me and adding 13 additional files to the project
just to access the service is not ideal, so, I decided to came up with this library.

Usage
-----
The main idea here is to be as simple as possible, basically you just instantiate the library and execute
any of the methods in it, I've implemented all the public API methods available for the moment.

	// Configuration options
	$config['stripe_key_test_public']         = '';
	$config['stripe_key_test_secret']         = '';
	$config['stripe_key_live_public']         = '';
	$config['stripe_key_live_secret']         = '';
	$config['stripe_test_mode']               = TRUE;
	$config['stripe_verify_ssl']              = FALSE;

	// Create the library object
	$stripe = new Stripe( $config );

	// Run the required operations
	echo $stripe->customer_list();

That's it! Have fun.

Codeigniter
-----------
Oh by the way! This library is completely functional as standalone but I developed it as a Codeigniter library,
to use it that way you simply create a config file in: {APPLICATION}/config/stripe.com to store the config array.
Then is just the usual deal that you already know and love!

	$this->load->library( 'stripe' );
	echo $this->stripe->customer_list();
