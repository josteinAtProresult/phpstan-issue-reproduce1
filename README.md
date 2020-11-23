phpstan issue reproduction
==========================

phpstan incorrectly reports error when scanned codebase has two separate functions with same name, but different signature.

Even though the duplicate2.php file is not included in duplicate1, phpstan reports error as if the code in duplicate1 is calling the function in duplicate2.php instead of the one declared within duplicate1.php.

To run reproduction in docker:

    docker run -v <PATH_TO_CHECKOUT_DIR>:/mnt:ro --name phpstan-issue1 -w /mnt phpstan/phpstan analyse
    
Result:
-----------------------

    Line   duplicate1.php                                            
    8      Function duplicate invoked with 1 parameter, 2 required.  

                                                                                

                                                                                

