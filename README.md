# Trabajo-en-parejas
repo del trabajo en equipo


---------- feature-missions ----------

let misiones = [
  "Hackeo de datos",
  "Escolta",
  "Intrusión en red corporativa",
];

//Calculamos la recompensa, aplicamos return
function calcularRecompensa(dificultad, bono = 500) {
  const base = dificultad * 1000; 
  const total = base + bono;
  return total;
}

// Hacemos simulación de peligro, se ocupa do-while
function simularPeligro() {
  let intentos = 0;
  let numero;
  let log = [];

  do {
    numero = Math.floor(Math.random() * 10) + 1; // 1-10
    intentos++;
    log.push(`Intento ${intentos}: señal=${numero}`);
    // Detener cuando el número aleatorio sea > 8 o 5 intentos
  } while (numero <= 8 && intentos < 5);

  const estado = numero > 8 ? "ALTO" : "MODERADO";
  return {
    intentos,
    ultimaSeñal: numero,
    nivelPeligro: estado,
    log
  };
}

// Validamos la misión con if-else (legal/ilegal)
function validarMision(nombreMision) {
  const ilegales = [
    "Robo de datos",
    "Sabotaje industrial",
    "Intrusión en red corporativa"
  ];
  const legales = [
    "Escolta",
    "Auditoría de seguridad",
    "Recuperación de credenciales"
  ];

  if (ilegales.includes(nombreMision)) {
    return { nombre: nombreMision, legalidad: "Ilegal" };
  } else if (legales.includes(nombreMision)) {
    return { nombre: nombreMision, legalidad: "Legal" };
  } else {
    return { nombre: nombreMision, legalidad: "Desconocida" };
  }
}
