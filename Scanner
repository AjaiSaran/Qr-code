<!DOCTYPE html>
<html>
  <head>
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css">
        <link rel="stylesheet" href="styleApp.css" type="text/css">
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/js/bootstrap.min.js"></script>
        <title>Ticket APP</title>
        <link rel="icon" href="favicon.png" type="img/icon">
        <script type="text/javascript" src="https://rawgit.com/schmich/instascan-builds/master/instascan.min.js" ></script>	
    
    <?php
        session_start();
        if(isset($_POST["submit"])){
            $_SESSION['qrCode']=$_POST["qrCode"];
            header("Location: ./index.php");
        }
        
    ?>

</head>
  <body>
      
    <img class="img-responsive" id="pullingo" src="A.png" width="30%">
    <div id="details">
    <video id="preview"></video>
    <form action="qrcode.php" method="post">
        <input type=text name="qrCode" id="qr_code">
        <button name="submit">submit Qr</button>
    </form>
</div>
    <script>
        let scanner = new Instascan.Scanner(
            {
                video: document.getElementById('preview')
            }
        );
        scanner.addListener('scan', function(content) {
            alert('qrcode : ' + content);
            window.open(content, "_blank");
            var input = document.getElementById("qr_code");
            input.value=content;
        });
        Instascan.Camera.getCameras().then(cameras => 
        {
            if(cameras.length > 0){
                scanner.start(cameras[1]);
            } else {
                console.error("No QR");
            }
        });
    </script>

 </body>
</html>
