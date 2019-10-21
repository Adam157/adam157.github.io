---
layout: post
title: 'The site is experiencing technical difficulties'
date: 2019-06-06
published: true
---



The site is experiencing technical difficulties.

The site is experiencing technical difficulties. Please check your site admin email inbox for instructions.

Step 1

Turn on debugging via wp-config

Step 2

if this is the issue

stderr: PHP Catchable fatal error:  Object of class WP_Error
could not be converted to string in
/yourpath/wp-includes/default-constants.php on line 131

function wp_plugin_directory_constants() {
    if ( !defined('WP_CONTENT_URL') )
        define( 'WP_CONTENT_URL', get_option('siteurl') . '/wp-content');
        
To check use sql - SELECT * FROM `wp_options` WHERE option_name = 'siteurl';

Example returned corrupted value 

O:8:"WP_Error":2:{s:6:"errors";a:1:{s:30:"wpdb_get_table_charset_failure";a:1:{i:0;s:0:"";}}s:10:"error_data";a:0:{}}



Step 3

define( 'DB_NAME', 'my_wordpress' );
/** MySQL database username */
define( 'DB_USER', 'my_wpuser' );
/** MySQL database password */
define( 'DB_PASSWORD', 'mypassword' );
/** MySQL hostname */
define( 'DB_HOST', 'localhost' );
/** Database Charset to use in creating database tables. */
define( 'DB_CHARSET', 'utf8' );
/** The Database Collate type. Don't change this if in doubt. */
define( 'DB_COLLATE', '' );

wp_7r9md92ryn_options





UPDATE wp_7r9md92ryn_optiexons SET option_value = 'https://mywordpress.com' WHERE option_name = 'siteurl';
