# PoC IPTV Smarters Exploit

## Usage
`python gld.py -u http://www.pirate-ilegal-tv.com/ -i`


## Vulnerability 

### file `includes/ajax-control.php`:
```
<?php
/*
 * @ PHP 5.6
 * @ Decoder version : 1.0.0.1
 * @ Release on : 24.03.2018
 * @ Website    : http://EasyToYou.eu
 */

session_start();
if (file_exists("functions.php")) {
    include_once "functions.php";
    if (isset($_FILES["logoImage"])) {
        $target_dir = "../images/";
        $target_file = $target_dir . basename($_FILES["logoImage"]["name"]);
        if (move_uploaded_file($_FILES["logoImage"]["tmp_name"], $target_file)) {
            echo "images/" . $_FILES["logoImage"]["name"];
            exit;
        }
        echo "errorImage";
        exit;
    }
 ```

## Screenshot
![screenshot](screenshot.png)

## Shell Script Interactive in Python.
![](CVE-2020-9083.gif)



