<script>
    let segundos = 0; 
    let intervalo = null;
  
    // Función para empezar el cronómetro
    function empezar() {
      if (!intervalo) {
        intervalo = setInterval(function() {
          segundos += 1; 
        }, 1000);
      }
    }
  
    // Función para pausar el cronómetro
    function pausar() {
      clearInterval(intervalo); 
      intervalo = null; 
    }
  
    // Función para reiniciar el cronómetro
    function reiniciar() {
      clearInterval(intervalo); 
      intervalo = null; 
      segundos = 0; 
    }
  </script>
  
  <style>
    div {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }
    button {
      margin: 5px;
      padding: 10px;
      font-size: 14px;
    }
    h1 {
      font-size: 36px;
      margin-top: 20px;
    }
  </style>
  
  <div>
    <h2>Cronómetro</h2>
  
    <div>
      <!-- Botones de control -->
      <button on:click={empezar}>Iniciar</button>
      <button on:click={pausar}>Pausar</button>
      <button on:click={reiniciar}>Reiniciar</button>
    </div>
  
    <!-- Mostrar el tiempo en formato MM:SS -->
    <h1>
      {Math.floor(segundos / 60)}:{(segundos % 60).toString().padStart(2, '0')}
    </h1>
  </div>