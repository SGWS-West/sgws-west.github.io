<!DOCTYPE html>
<html>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(to top left,#FFFFFF, #252524);
      background-repeat: space;
      height: 60vh;
      color: white;

    }

    .formContainer {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      color: white;
      border-radius: 8px 8px;
      height: 100%;
      width: 100%;
      font-family: 'Roboto', sans-serif;
    }

    .formContainer h1 {
      padding: 2vh;
    }

    input {
      margin-bottom: 5vh;
      border-right: none;
      border-top: none;
      border-left: none;
      background-color:transparent;
      outline: none;
      color: white;
      caret-color: white;
    }

    input[type=text]::placeholder {
      text-align: center;
      color: white;
      font-family: 'Roboto', sans-serif;
    }

    input[type=submit] {
      background: rgba(255,255,255,.2);
      width: 100%;
      padding: 2vh;
      border: none;
      cursor: pointer;
      border-rad
  </style>

  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css?family=Roboto:100" rel="stylesheet">
    <title>SGWS QR Code Generator</title>
  </head>

  <body id="body">
    <div class="formContainer">
      <form onSubmit=generate()>

        <input type="text" id="menu_url" name="menu_url" placeholder="Menu URL" onfocus="this.value=''" onblur="this.placeholder='Menu URL'"><br>

        <br>
        <input type="submit" value="Submit">
      </form>
    </div>
  </body>
  
  <script>
    function formSubmit(event) {
      console.log("Submitted");
      event.preventDefault();
    };
    
    function generate() {
	var qr_gen_url = "https://api.qrserver.com/v1/create-qr-code/?data=";
    var button = document.getElementById('qr');
    var url = document.getElementById('menu_url');
    var qr_url = qr_gen_url + url.value;
    window.open(qr_url, "", "width=350,height=350");
    event.preventDefault();
};
  </script>

</html>