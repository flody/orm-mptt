## Modified Preorder Traversal Tree for Kohana 3.3 ORM

A port of Banks' Sprig_MPTT plus some code from BIakaVeron's ORM_MPTT module.

[ISC License](http://www.opensource.org/licenses/isc-license.txt)

### Setup

Place module in /modules/ and include the call in your bootstrap.

### Declaring your ORM object

	class Model_Category extends ORM_MPTT {
	}


### Usage Examples

#### Creating a root node:

	$cat = ORM::factory('Category_Mptt');
	$cat->name = 'Music';
	$cat->insert_as_new_root();
	echo 'Category ID'.$mptt->id.' set at level '.$cat->lvl.' (scope: '.$cat->scope.')';
	$c1 = $cat; // Saving id for next example

#### Creating a child node:

	$cat->clear(); // Clearing ORM object
	$cat->name = 'Terminology';
	$cat->insert_as_last_child($c1);
 
### Authors 
 * Mathew Davies
 * Kiall Mac Innes
 * Paul Banks
 * Brotkin Ivan
 * Brandon Summers
 * Alexander Yakovlev

