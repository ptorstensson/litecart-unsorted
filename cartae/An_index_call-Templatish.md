app_header.inc.php
===
FS_DIR_HTTP_ROOT . WS_DIR_INCLUDES
WS_DIR_CLASSES
vmod::check
WS_DIR_CONTROLLERS
WS_DIR_MODULES
WS_DIR_FUNCTIONS
WS_DIR_REFERENCES
WS_DIR_ROUTES
function error_handler
WS_DIR_HTTP_HOME
debug_backtrace()
system::init()
system::run( $method );





default.inc.php
===
document::$snippets['bottom'] is defined as a cookie div messageblob..

WS_DIR_EXT
WS_DIR_HTTP_HOME
{snippet:language}
{snippet:title}
{snippet:charset}
{snippet:description}
{snippet:template_path}
<!--snippet:head_tags-->
<!--snippet:styles-->
<!--snippet:javascript-->
document::$settings[ 'fixed_header' ]
document::href_ilink( '' )
WS_DIR_IMAGES
settings::get('store_name')
FS_DIR_HTTP_ROOT . WS_DIR_BOXES
<!--snippet:notices-->
<!--snippet:top-->
<!--snippet:column_left-->
<!--snippet:content-->
<!--snippet:bottom-->
functions::draw_fonticon('fa-chevron-circle-up fa-3x', 'style="color: #000;"')
<!--snippet:foot_tags-->



index.inc.php
===
<!--snippet:box_slider-->
<!--snippet:box_manufacturer_logotypes-->
<!--snippet:box_most_popular_products-->
<!--snippet:box_campaign_products-->
<!--snippet:box_latest_products-->



box_region.inc.php + view
===
functions::draw_fancybox('.fancybox-region', array(
	'centerOnScroll' => true,
	'hideOnContentClick' => false,
	'modal' => false,
	'speedIn' => 600,
	'transitionIn' => 'fade',
	'transitionOut' => 'fade',
	'type' => 'ajax',
	'scrolling' => 'false',
));
language::$selected['code']
language::$selected['name']
currency::$selected['name']
currency::$selected['code']
functions::reference_get_country_name(customer::$data['country_code'])
document::href_ilink('regional_settings')
language::translate('title_change', 'Change')



box_cart.inc.php + view
===
document::ilink('checkout')
cart::$total['items']
customer::$data['display_prices_including_tax']
currency::format(cart::$total['value'])
cart::$total['tax']
snippet:template_path
language::translate('title_cart', 'Cart')
language::translate('text_items', 'item(s)')
language::translate('title_checkout', 'Checkout')
document::ilink('ajax/cart.json')
language::$selected['charset']



box_site_menu.inc.php + view
===
cache::cache_id('box_site_menu', ... ) 
cache::capture($box_site_menu_cache_id, 'file')

functions::draw_fonticon('fa-home', ... )
language::translate('title_home', 'Home')
function custom_site_menu_category_tree()
database::fetch()
document::ilink('category', array('category_id' => $category['id']))
functions::image_thumbnail( './' . $category['image'], 24, 24, 'CROP')
DB_TABLE_CATEGORIES
database::num_rows()
custom_site_menu_category_tree($category['id'], $depth+1, $output[$category['id']]['subitems'])
database::free()
$box_site_menu->snippets['items']
DB_TABLE_PAGES
DB_TABLE_PAGES_INFO
language::$selected['code']
document::ilink('information', array('page_id' => $page['id']))
cache::end_capture()
function custom_draw_site_menu($items, $indent=0)
custom_draw_site_menu($item['subitems'], $indent+1)
custom_draw_site_menu($items)



column_left.inc.php
===
functions::draw_fonticon('fa-bars')
<!--snippet:box_search-->
<!--snippet:box_category_tree-->
<!--snippet:box_filter-->
<!--snippet:box_recently_viewed_products-->
<!--snippet:box_account-->



box_search.inc.php
===
functions::form_draw_form_begin( 'search_form', 'get', document::ilink( 'search' ) )
functions::draw_fonticon( 'fa-search' )
functions::form_draw_search_field( 'query', true, 'placeholder="' . language::translate( 'text_search_phrase_or_keyword', 'Search phrase or keyword' )
functions::form_draw_form_end()



box_category_tree.inc.php
===
cache::cache_id('box_category_tree', ... )
cache::capture($box_category_tree_cache_id, 'file')
functions::catalog_category_trail(empty($_GET['category_id']) ? 0 : $_GET['category_id']))
function output_category_tree($category_id, $level, $category_trail, &$output)
functions::catalog_categories_query($category_id)
language::translate('title_categories', 'Categories')
custom_draw_category_tree($categories, $indent=0)
functions::draw_fonticon(!empty($category['opened']) ? 'fa-minus-square' : 'fa-plus-square', 'style="font-size: 0.9em;"')
custom_draw_category_tree($category['subcategories'], $indent+1)
custom_draw_category_tree($categories)



box_filter.inc.php + view
===
route::$route['page']
DB_TABLE_PRODUCTS
DB_TABLE_MANUFACTURERS
DB_TABLE_PRODUCTS_TO_CATEGORIES
database::input(language::$selected['code'])
DB_TABLE_PRODUCT_GROUPS_VALUES_INFO
functions::form_draw_form_begin('filter_form', 'get')
language::translate('title_manufacturers', 'Manufacturers')
functions::form_draw_checkbox('manufacturers[]', $manufacturer['id'], true)
functions::form_draw_checkbox('product_groups[]', $group['id'].'-'.$value['id'])
functions::form_draw_form_end()



box_recently_viewed_products.inc.php
===
session::$data['recently_viewed_products']
settings::get('box_recently_viewed_products_num_items')
settings::get('box_recently_viewed_products_num_items')



app_footer.inc.php
===
$page = new view()
document::$layout
$page->snippets[]
$page->stitch()
$page->snippets = document::$snippets
settings::get('jobs_last_push')
settings::get('jobs_interval')
settings::get('jobs_last_run')
settings::get('jobs_interval')
database::query( string ) 
document::ilink('push_jobs')
