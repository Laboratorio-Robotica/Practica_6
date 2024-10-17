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
Esta práctica ayudó para un mejor entendimiento de la parte teórica en el manejo de motores mediante un driver. Determinar la configuración del driver permitió entender cómo los ajustes específicos influyen en la programación, lo que fue clave para el desarrollo del código con el fin de hacer girar el motor en la dirección y tiempo deseado. Al finalizar, se alcanzaron los objetivos planteados y se entendió el funcionamiento de los drivers y la programación.


### Pablo Axel Silva Fuentes: 
De primera instancia la práctica fue esencial para reforzar los conocimientos teóricos adquiridos en clase, ya que permitió experimentar de manera directa con los conceptos relacionados con el funcionamiento de los drivers. Al usar el Arduino UNO, se profundizó en la configuración específica del driver, lo que facilitó la creación de un código ajustado a las necesidades del sistema ya que este puede variar. El desarrollo del código demuestra que la práctica no solo alcanzó los objetivos propuestos, sino que también ayudo un aprendizaje aplicable de manera practica.


### Eduardo David Salas Ayala:
Esta práctica ayudo significativamente a la comprensión de los conceptos tratados en las clases teóricas, facilitando la conexión entre la parte teoría y la parte práctica. Permitió entender mejor el funcionamiento de los drivers utilizando una placa de desarrollo. Durante su desarrollo, se analizó en detalle la configuración del driver, ya que la programación variaba según los ajustes específicos. Basándonos en la configuración que se nos proporcionó, se desarrolló el código correspondiente, tomando en cuenta estos aspectos. Como resultado, se concluyó que la práctica se realizó de manera efectiva, alcanzando los objetivos propuestos y logrando el aprendizaje esperado.

## Referencias bibliográficas
- Epson (2020). EPSON RC+ 7.0 Manual del usuario Administración y desarrollo de proyectos (Ver.7.3). https://files.support.epson.com/far/docs/epson_rc_pl_70_users_guide_spanish_(v73r2).pdf
