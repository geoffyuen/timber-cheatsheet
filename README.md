Timber Cheatsheet
=================

Because remembering the "Timber" way can be hard.

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
	
Or get rid of the container completely:

.twig:

	{{ function("wp_nav_menu", "&theme_location=main_menu&container=false") }}
	
--	

## ACF Image (set to return an ID)

`<img src="{{ TimberImage(youracfthing.theimageidholder).src | resize(150) }}" alt="">`

## Srcset

https://github.com/MINDKomm/Timmy

You can do this:

    <img{{ post.thumbnail|get_timber_image_responsive('custom-6') }}>

To get this:

    <img srcset="http://www.mind.ch/wp-content/uploads/2016/02/header_example-480x206-c-default.jpg 480w,
    http://www.mind.ch/wp-content/uploads/2016/02/header_example-768x329-c-default.jpg 768w,
    http://www.mind.ch/wp-content/uploads/2016/02/header_example-1400x600-c-default.jpg 1400w,
    http://www.mind.ch/wp-content/uploads/2016/02/header_example-2800x1200-c-default.jpg 2800w"
    sizes="100vw" alt="Your alt text" title="Your image title">
