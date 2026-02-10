index.html  
  
<!DOCTYPE html>  
<html lang="es">  
<head>  
<meta charset="UTF-8">  
<title>ENTREGA</title>  
<meta name="viewport" content="width=device-width, initial-scale=1">  
<style>  
body { font-family: Arial; background:#f5f5f5; margin:0; padding:15px;}  
.card { background:#fff; padding:15px; margin-bottom:10px; border-radius:8px;}  
button { padding:10px; width:100%; margin-top:8px; }  
input { width:100%; padding:8px; }  
.done { color:green; font-weight:bold; }  
</style>  
</head>  
  
<body>  
<h2>ENTREGA</h2>  
  
<div class="card">  
<input id="task" placeholder="Ej: Lengua - resumen - viernes">  
<button onclick="addTask()">Agregar tarea</button>  
</div>  
  
<div id="tasks"></div>  
  
<script>  
let tasks = [];  
  
function addTask(){  
  let t = document.getElementById("task").value;  
  if(!t) return;  
  tasks.push({name:t, done:false});  
  document.getElementById("task").value="";  
  render();  
}  
  
function render(){  
  let html="";  
  tasks.forEach((t,i)=>{  
    html+=`  
    <div class="card">  
      <strong>${t.name}</strong><br>  
      <label><input type="checkbox"> Leer</label><br>  
      <label><input type="checkbox"> Hacer</label><br>  
      <label><input type="checkbox"> Revisar</label><br>  
      <input type="file" accept="image/*">  
      <button onclick="verify(${i})">Verificar</button>  
      <div id="v${i}"></div>  
    </div>`;  
  });  
  document.getElementById("tasks").innerHTML = html;  
}  
  
function verify(i){  
  document.getElementById("v"+i).innerHTML =  
    "<span class='done'>✔ Evidencia cargada</span>";  
}  
</script>  
</body>  
</html>  
