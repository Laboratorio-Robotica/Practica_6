# Practica_6
## Integrantes:  
- Francisco Javier Godinez Lopez
- Pablo Axel Silva Fuentes
- Eduardo David Salas Ayala
## Introducción:  

La práctica tiene como obejtivo programar el control de giro de un motor a través del uso de un driver modelo JSSD2505M, el cual se encuentra configurado para operar a una resolución de 800 pulsos por revolución. Para llevar a cabo la tarea, se utilizará una placa Arduino UNO, que será el encargado de gestionar la secuencia de pulsos que deberá enviar al driver, además de controlar parámetros como el tiempo de operación y la velocidad de rotación del motor. El Arduino permitirá ajustar estos parámetros de manera precisa, facilitando así la configuración del sistema para diferentes aplicaciones que requieran un control preciso del motor. De este modo, se podrá evaluar el comportamiento del sistema bajo diversas condiciones de carga y velocidad, optimizando el desempeño del motor de acuerdo con los requerimientos del proyecto.

## Instrucciones

El motor debe completar una serie de movimientos programados, los cuales se describen a continuación:

1. El motor debe girar dos veces en sentido horario (hacia la derecha) dentro de un intervalo de 3 segundos,
2. Posteriormente, el motor debe realizar dos giros en sentido antihorario (hacia la izquierda) en un intervalo de 2 segundos.
   


De tal manera que el codigo desarrollado del Arduino IDE quedo de la siguiente manera:
```
const int PinDir = 4;
const int PinPul = 3;
const int pulsos = 800;

void setup() {
   pinMode(PinDir, OUTPUT);
   pinMode(PinPul, OUTPUT);
}

void Vueltas(int direccion, int pasos, int Tiempo) {
  digitalWrite(PinDir, direccion);
  for (int i = 0; i < pasos; i++) {
    digitalWrite(PinPul, HIGH); 
    digitalWrite(PinPul, LOW);
    delay(Tiempo);        
  }
}

void loop() {
  Vueltas(LOW, pulsos, 1000 / pulsos);
  Vueltas(LOW, pulsos, 1000 / pulsos);

  delay(1000); 

  Vueltas(HIGH, pulsos, 2000 / pulsos);
  Vueltas(HIGH, pulsos, 2000 / pulsos);

  delay(1000);  
}
```



En el siguiente video se muestra el movimiento realizado utilizando el código anterior, cuyo objetivo fue realizar una cantidad de giros en un lapso de tiempo estipulado por el profesor. Este proceso demuestra el correcto funcionamiento del sistema y cumple con los objetivos establecidos para la práctica

[https://drive.google.com/file/d/1aWOLuFcHtRlWnIL43TMY93QTWtS5U5pO/view?usp=sharing link](https://drive.google.com/file/d/1aWOLuFcHtRlWnIL43TMY93QTWtS5U5pO/view?usp=sharing)

## Conclusiones:  
### Francisco Javier Godinez Lopez:
La práctica fue importante para comprender la programación de trayectorias del brazo robótico Epson utilizando comandos como Move, Go, y Arc3. El ejercicio permitió aplicar estos comandos de manera secuencial para escribir la palabra "Taco", lo que reforzó el conocimiento de los diferentes tipos de movimientos y cómo  afecta la precisión del robot, cumpliendo satisfactoriamente con los objetivos planteados.


### Pablo Axel Silva Fuentes: 
La práctica fue crucial para entender cómo se pueden combinar los diferentes comandos de movimiento del brazo robótico Epson para lograr una tarea precisa como escribir "Taco". A través del uso de Move y Arc3, se aprendió a controlar los movimientos del robot con exactitud. Además, el descubrimiento de la posibilidad de ajustar directamente los puntos en el código hizo que fuera más fácil optimizar el trabajo en el eje Z, mejorando el proceso de escritura y contribuyendo al éxito del proyecto.


### Eduardo David Salas Ayala: 
Esta práctica permitió una mejor comprensión de cómo se utilizan los comandos básicos y avanzados de movimiento en el software Epson RC+ para controlar el brazo robótico. El uso de Go, Move, y Arc3 para escribir la palabra "Taco" fue un ejercicio clave para aplicar los conocimientos adquiridos. También se aprovechó la función de ajustar la posición Z directamente en el código, lo que simplificó la edición de los puntos y ayudó a refinar los movimientos del robot.

## Referencias bibliográficas
- Epson (2020). EPSON RC+ 7.0 Manual del usuario Administración y desarrollo de proyectos (Ver.7.3). https://files.support.epson.com/far/docs/epson_rc_pl_70_users_guide_spanish_(v73r2).pdf
