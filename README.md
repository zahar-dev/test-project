# test-project

to setup laravel project :-

composer create-project laravel/laravel my-laravel-app

to run laravel project :- php artisan serve

=============================================================================================
to include css and js file in blade file then change the css and js folder path 
to public folder :-

to css file use this :- <link rel="stylesheet" href="{{ asset('css/styles.css') }}">
to js file use this :- <script src="{{ asset('js/script.js') }}"></script>

==============================================================================================

to add database in .env file :-

DB_CONNECTION=mysql //add this
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel-practice   //your database name
DB_USERNAME=root
DB_PASSWORD=

getting session table issue use this :-
-> php artisan session:table
-> php artisan migrate

==============================================================================================

create product table and product_size table model and migrate :-

-> php artisan make:model
	model Products
	migration,resources	
	
	
add table fields in mirgation table file :-
        Schema::create('products', function (Blueprint $table) {
            $table->id();
            $table->string('name');
            $table->decimal('price', 10, 2);
            $table->string('mfg_code');
            $table->timestamps();
        });	
	
=> 	php artisan migrate

-> php artisan make:model 
	model Product_sizes
	migration
	
add table fields in mirgation table file :-
        Schema::create('products', function (Blueprint $table) {
            $table->id();
            $table->string('name');
            $table->decimal('price', 10, 2);
            $table->string('mfg_code');
            $table->timestamps();
        });	
		
		
=> php artisan migrate  
table will be created.

===============================================================================================

to create the seeder file use this command :-

=> php artisan make:seeder ProductSeeder 

run this command to insert data into the database

=> php artisan db:seed --class=ProductSeeder

then add code in ProductSeeder file.


================================================================================================

new way to create an api in laravel 12

when you have migrate the or insert the data into the database then use this command

=> php artisan install:api
================================================================================================
task:- 2

<?php

$inputArray = [1, 2, 2, 3, 4, 4, 5, 1, 6];

// Empty array to store unique values
$uniqueArray = [];

foreach ($inputArray as $item) {
    if (!in_array($item, $uniqueArray)) {
        $uniqueArray[] = $item;
    }
}

print_r($uniqueArray);


or


$inputArray = [1, 2, 2, 3, 4, 4, 5, 1, 6];
$uniqueArray = array_keys(array_flip($inputArray));

print_r($uniqueArray);

====================================================
loop se sort

$inputArray = [1, 2, 2, 3, 4, 4, 5, 1, 6];
$uniqueArray = array_keys(array_flip($inputArray));
print_r($uniqueArray);


<?php

$array = [5, 3, 8, 1, 2];
$n = count($array);

// Bubble Sort
for ($i = 0; $i < $n - 1; $i++) {
    for ($j = 0; $j < $n - $i - 1; $j++) {
        if ($array[$j] > $array[$j + 1]) {
            // Swap
            $temp = $array[$j];
            $array[$j] = $array[$j + 1];
            $array[$j + 1] = $temp;
        }
    }
}

print_r($array);



