class.html.php	
=======================================================================================
Based on https://davidwalsh.name/create-html-elements-php-htmlelement-class


FORM EXAMPLE
=======================================================================================

$theform=new htmlForm("test.php");
$theform->addInput("Label 1",array('name' => 'number1', 'value' => ''));
$theform->addInput("Label 2",array('name' => 'number2', 'value' => ''));
$theform->addTextarea("Label 3",array('name' => 'number3'),"The text in the textarea");
$theform->addCheckboxes("Label 4","favorite_color",array('r' => 'Red', 'g' => 'Green', 'b' => 'Blue'), array('g'));
$theform->addSelect("Label 5","favorite_color",array('r' => 'Red', 'g' => 'Green', 'b' => 'Blue'), array('g'));
echo $theform->render();

LIST EXAMPLE
=======================================================================================

$standardlist=new htmlList();
$standardlist->listItem("Item 1");
$standardlist->listItem("Item 2");
$standardlist->listItem("Item 3");
$standardlist->listItem("Item 4");
echo $standardlist->render();

$definitionlist=new htmlList('dl');
$definitionlist->listItem(array("Title 1","Definition 1"));
$definitionlist->listItem(array("Title 2","Definition 2"));
$definitionlist->listItem(array("Title 3","Definition 3"));
echo $definitionlist->render();

Zurb Foundation Card
=======================================================================================

$card=new zurbCard();
$card->section('Header','card-divider',array('class' => 'a_class'));
$card->section('Content');
echo $card->render();

=======================================================================================

// Standard usage
$tabledata=array(
	array('color' => 'Red', 'animal' => 'Fox', 'car' => 'Ferrari'), 
	array('color' => 'Green', 'animal' => 'Chameleon', 'car' => 'Skoda'), 
	array('color' => 'Blue', 'animal' => 'Seal', 'car' => 'Volvo') 
);

// An array with numerical indexes will not print table header
$tabledata_nocols=array(
	array('a','b','c'), 
	array('alpher','bethe','gamow'), 
	array('coke','pepsi','jolt') 
);

// Advanced usage: individual cells can be targeted by sending the value as an array containing cell content in 'text' and additional attributes as an array under 'attrib'
$tabledata_advanced=array(
	array('color' => array('text' => 'Red', 'attrib' => array('style' => 'background-color: red;')), 'animal' => 'Fox', 'car' => 'Ferrari'), 
	array('color' => array('text' => 'Green', 'attrib' => array('style' => 'background-color: green;')), 'animal' => 'Chameleon', 'car' => 'Skoda'), 
	array('color' => array('text' => 'Blue', 'attrib' => array('style' => 'background-color: blue;')), 'animal' => 'Seal', 'car' => 'Volvo') 
);

$table=new htmlTable('Favorite colors');
$table->addData($tabledata);
echo $table->render();