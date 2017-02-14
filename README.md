Timber Cheatsheet
=================

## Because remembering the "Timber" way can be hard.

Menus using wp_nav_menu
-----------------------

### Register your menu locations:

functions.php:

	register_nav_menus( array(
		'main_menu' => 'Main Menu',
		'social_menu' => 'Social Menu'
	) );

Output them somewhere in your .twig file:

.twig:

	{{ function("wp_nav_menu", "&theme_location=main_menu") }}
	{{ function("wp_nav_menu", "&theme_location=social_menu") }}

Generated html:

	<div class="menu-main-container"><ul id="menu-main" class="menu"><li id="menu-item-18" class="menu-item menu-item-type-custom menu-item-object-custom current-menu-item current_page_item menu-item-home menu-item-18"><a href="//localhost:3000/sportsvault.ca">Home</a></li>
	<li id="menu-item-93" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-93"><a href="#catalogues">Catalogues</a></li>
	<li id="menu-item-94" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-94"><a href="#about">About</a></li>
	<li id="menu-item-95" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-95"><a href="#contact">Contact</a></li>
	</ul></div>

Change the `div` wrapper to `nav` element for semantic html:

.twig:

	{{ function("wp_nav_menu", "&theme_location=main_menu&container=nav") }}
	
--	

### ACF Image (set to return an ID)

`<img src="{{ TimberImage(youracfthing.theimageidholder).src | resize(150) }}" alt="">`
