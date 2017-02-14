Timber Cheatsheet
=================

Menus using wp_nav_menu
-----------------------

Register your menu locations:

functions.php:

	register_nav_menus( array(
		'main_menu' => 'Main Menu',
		'social_menu' => 'Social Menu'
	) );

Output them somewhere in your .twig file:

.twig:

	{{ function("wp_nav_menu", "&theme_location=main_menu") }}
	{{ function("wp_nav_menu", "&theme_location=social_menu") }}
