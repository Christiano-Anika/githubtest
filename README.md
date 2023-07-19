# githubtest
<?php

/* 
   Plugin Name : Custom Plugin
   Author: Maria
   Version: 0.0.1
   Description: This is custom plugin

*/

// define primary path info
// first argument is any unique name
// 2nd argument is function to access root directory

define('WCP_dir',dirname(__FILE__));
define('WCP_url',plugins_url('',__FILE__));


//we use 2 built in functions
add_action('admin_menu','WCP_custom_function1');
add_action('admin_enqueue','WCP_reg_stylesheet');
add_action('admin_enqueue_scripts','WCP_reg_scripts');


// Add Menu functions
function WCP_custom_function1() {
   // 1st part of function


/*  this is complete list

    add_menu_page(
    add_dashboard_page(
    add_posts_page( 
    add_pages_page(   
    add_comments_page(  
    add_plugins_page(
    add_users_page(      

*/

   add_menu_page(    
      // 2nd part of function
                  'WCP_custom plugin', // Page Title
                  'WCP_Custom Plugin', // Menu Title
                  'manage_options', // capability
                  'WCP_custom_plugin_page', // menu slug
                  'WCP_custom_function2', // callable function
                  WCP_url.'icon.png' // icon URL later add

        );
}
function WCP_custom_function2() {

     include_once(WCP_dir.'WCP_php_design.php'); // both ar in same folder
     php_design();   
}

// Add style sheets

// callable function in which CSS file will be registered
function WCP_reg_stylesheets(){

   wp_enqueue_style('WCP_cover_stylesheet',WCP_url.'WCP_css_stylesheet.css');

}

function WCP_reg_scripts() {

   wp_enqueue_script('WCP_js_jquery_file',WCP_url.'WCP_is_jquery.js');
   wp_enqueue_script('WCP_js_jquery_file',WCP_url.'WCP_is_jquery2.js');

}

jnknklmm;o;okjjo

?>