
# 18/08/2017

http://php.net/manual/en/function.substr.php#114784


function str_ends($string,$end){
    return (substr($string,-strlen($end),strlen($end)) === $end);
}   
function str_begins($string,$start){
    return (substr($string,0,strlen($start)) === $start);
}   

Example:
if (str_ends ($filename, ".jpg")){
   echo "The extension is .jpg";
}