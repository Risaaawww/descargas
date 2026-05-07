<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Muro de Pi</title>

  <style>
    body{
      margin:0;
      background:black;
      color:white;
      font-family:Consolas, monospace;
      display:flex;
      flex-direction:column;
      justify-content:center;
      align-items:center;
      height:100vh;
      overflow:hidden;
    }

    h1{
      color:lime;
      margin-bottom:30px;
      text-align:center;
    }

    #pi{
      width:80%;
      font-size:24px;
      word-wrap:break-word;
      text-align:center;
      border:2px solid lime;
      padding:20px;
      border-radius:10px;
      background:#111;
      min-height:120px;
    }
  </style>
</head>
<body>

  <h1>Presiona ESPACIO para revelar Pi</h1>

  <div id="pi"></div>

  <script>
    const pi =
      "3.14159265358979323846264338327950288419716939937510" +
      "58209749445923078164062862089986280348253421170679" +
      "82148086513282306647093844609550582231725359408128" +
      "48111745028410270193852110555964462294895493038196";

    let cantidad = 1;

    const muro = document.getElementById("pi");
    muro.textContent = pi.slice(0, cantidad);

    document.addEventListener("keydown", (e) => {
      if (e.code === "Space") {
        e.preventDefault();

        cantidad += 5;

        if (cantidad > pi.length) {
          cantidad = pi.length;
        }

        muro.textContent = pi.slice(0, cantidad);
      }
    });
  </script>

</body>
</html>
