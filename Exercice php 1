<!doctype HTML>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercice</title>
</head>
<body>
<center><button onclick="window.print();"><span>print page</span></button></center>
<center>
<?php
    session_start();
    $etudiant = array();
    $f = fopen('elevesYM2.csv','r');
    while($l=fgetcsv($f)){
     array_push($etudiant,array($l[0],$l[1]));}
    function myfunc($debut,$fin,$etudiant){
        for($i=$debut;$i<=$fin;$i++){
            for($j=0;$j<2;$j++){
                echo $etudiant[$i][$j];
                if($j == 1 && ! (empty($etudiant[$i]))){ ?>
        <table>
            <tr>
                <td>
                    Enoncé
                    <table border=1>
                    <?php $a = random_int(150,900);
                    $b = random_int(150,900);
                    $c = random_int(150,900);
                    $d = random_int(150,900);?>
                        <tr>  <td>Bin</td>  <td>Dec</td>  <td>Hex</td>  <td>Oct</td>  </tr>
                        <tr>  <td><?php echo decbin($a) ?></td>  <td><?php echo '...........'?></td>  <td><?php echo '...........' ?></td>  <td><?php echo '...........' ?></td>  </tr>
                        <tr>  <td><?php echo '...........' ?></td>  <td><?php echo $b ?></td>  <td><?php echo '...........' ?></td>  <td><?php echo '...........' ?></td>  </tr>
                        <tr>  <td><?php echo '...........' ?></td>  <td><?php echo '...........' ?></td>  <td><?php echo dechex($c) ?></td>  <td><?php echo '...........' ?></td>  </tr>
                        <tr>  <td><?php echo '...........' ?></td>  <td><?php echo '...........' ?></td>  <td><?php echo '...........' ?></td>  <td><?php echo decoct($d) ?></td>  </tr>  
                    </table>
                </td>
                <td>
                    Corrigé
                    <table border=1>
                        <tr>  <td>Bin</td>  <td>Dec</td>  <td>Hex</td>  <td>Oct</td>  </tr>
                        <tr>  <td><?php echo decbin($a) ?></td>  <td><?php echo $a ?></td>  <td><?php echo dechex($a) ?></td>  <td><?php echo decoct($a) ?></td>  </tr>       
                        <tr>  <td><?php echo decbin($b) ?></td>  <td><?php echo $b ?></td>  <td><?php echo dechex($b) ?></td>  <td><?php echo decoct($b) ?></td>  </tr>
                        <tr>  <td><?php echo decbin($c) ?></td>  <td><?php echo $c ?></td>  <td><?php echo dechex($c) ?></td>  <td><?php echo decoct($c) ?></td>  </tr>
                        <tr>  <td><?php echo decbin($d) ?></td>  <td><?php echo $d ?></td>  <td><?php echo dechex($d) ?></td>  <td><?php echo decoct($d) ?></td>  </tr>
                    </table>
                </td>
            </tr>
        </table>    
        <?php }}}} ?>
    <?php
        if (empty($_POST) && ! isset($_SESSION['dp'])){
            $dp = 1;}
        else if (!empty($_POST)) {
            $fin = array_keys($_POST)[0];
            if (in_array($fin, array('next','bf'))){
                $dp=$_SESSION['dp'];
                if (strcmp($fin,'bf') && $dp < count($etudiant)-3){
                    $dp+=2;}
                else if (strcmp($fin,'next') && $dp>1) { 
                    $dp-=2; }} 
            else if(in_array($fin, array('next2', 'bf2'))){
                $dp = $_SESSION['dp'];
                if(strcmp($fin,'next2')){
                    $dp = 1;}
                else if(strcmp($fin,'bf2')){
                    if(count($etudiant)%2 == 0){
                        $dp = count($etudiant)-3;}
                    else {$dp = count($etudiant)-2;}}}
            else {$dp = intval($fin)*2-1;}} 
        else { $dp = $_SESSION['dp'];}
        $_SESSION['dp'] = $dp;
        $sp = $dp + 1;
        myfunc($dp, $sp, $etudiant); ?> 

    <form method="post">  
    <button name="bf2"> <span>&laquo;&laquo;</span> </button> 
        <button name="bf"> <span> &laquo; </span></button>
        <?php for($o=1; $o <= intval(count($etudiant)/2);$o++) {   
                if($o == intval(count($etudiant))/2 && count($etudiant)%2 == 0 ) {
                   break;}?>
        <input type="submit" name="<?php echo $o ?>" value="<?php echo $o ?>" > 
        <?php } ?> 
        <button name="next"><span>&raquo;</span></button>  
        <button name="next2"> <span>&raquo;&raquo;</span></button> 
        <p><?php echo $sp/2 ?></p> 
    </form> 
</body>
</html>
