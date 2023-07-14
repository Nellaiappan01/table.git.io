<!DOCTYPE html>
<html>
  <head>
    <title>Daily Report</title>
    <link href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,700" rel="stylesheet">
    <style>
      html, body {
      min-height: 100%;
      padding: 0;
      margin: 0;
      font-family: Roboto, Arial, sans-serif;
      font-size: 14px;
      color: #666;
      }
      h1 {
      margin: 0 0 20px;
      font-weight: 400;
      color: #1c87c9;
      }
      p {
      margin: 0 0 5px;
      }
      .main-block {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background: #1c87c9;
      }
      form {
      padding: 25px;
      margin: 25px;
      
      box-shadow: 0 2px 5px #f5f5f5; 
      background: #f5f5f5; 
      }
      .fas {
      margin: 25px 10px 0;
      font-size: 72px;
      color: #fff;
      }
      .fa-envelope {
      transform: rotate(-20deg);
      }
      .fa-at , .fa-mail-bulk{
      transform: rotate(10deg);
      }
      input, textarea {
    
      width: calc(70% - 18px);
      padding: 8px;
      margin-bottom: 20px;
      border: 1px solid #1c87c9;
      outline: none;
      }
      input::placeholder {
      color: #666;
      }
      button {
      width: 70%;
      padding: 10px;
      border: none;
      background: #1c87c9; 
      font-size: 16px;
      font-weight: 400;
      color: #fff;
      }
      button:hover {
      background: #2371a0;
      }    
      @media (min-width: 568px) {
      .main-block {
      flex-direction: row;
      }
      .left-part, form {
      width: 50%;
      }
      .fa-envelope {
      margin-top: 0;
      margin-left: 20%;
      }
      .fa-at {
      margin-top: -10%;
      margin-left: 65%;
      }
      .fa-mail-bulk {
      margin-top: 2%;
      margin-left: 28%;
      }
      }
    </style>
  </head>
  <body>
    <div class="main-block">
      <div class="left-part">
        <i class="fas fa-envelope"></i>
        <i class="fas fa-at"></i>


        <i class="fas fa-mail-bulk"></i>
      </div>
       


    <form method="post" id="form">
        <h1 style="color:rgb(29, 25, 219);font-size: 20px;font-weight: bolder;">ESCEE INDUSTRIES PRIVATE LIMITED </h1>
        <div id="res" style="color:green;font-size: 14px;"></div>
        <div>
            <input type="date" name="DATE" placeholder="date">
            <input class="fname" type="number" name="SCRAPPING" placeholder="SCRAPPING">
            <input type="number" name="PLANTGRADE" placeholder="PLANT GRADE">
            <input type="number" name="KALLUPPUGRADE" placeholder="KALLUPPU GRADE">
            <input type="number" name="RIDGESTOCK" placeholder="RIDGE STOCK 
          ">
        </div>
            <button name ="btn" type="submit" href="/">Submit</button>
      
    </div></form>
  </body>
  <script>
    let url ='https://script.google.com/macros/s/AKfycbwC4qA4Sc3YaNqCUmNapTzHZ3B_afXcFGUS5a4x7Ko4VIjVi8azAq7f4BzgQoeTc_8/exec';
    let form=document.querySelector('#form');
    form.addEventListener("submit",(e)=>{
        e.target.btn.innerHTML="Submitting.....";
        let d =new FormData(form);
        fetch(url,{method:"POST",
            body:d
        }).then((res)=>res.text())
        .then((finalRes)=>{
            e.target.btn.innerHTML="Submit";
            document.getElementById("res").innerHTML=finalRes;
            form.reset();
             setTimeout(()=>{
                document.getElementById("res").innerHTML=""; 
             },3000)        
        })
        e.preventDefault();
    })
    
  </script>
</html>
