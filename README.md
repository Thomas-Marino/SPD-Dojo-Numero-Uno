# Integrantes
- Gómez Lucas Iván.
- Góngora Lucas.
- Marino Thomas.
- Pacheco Matias.
- Sartorato Sebastian.
## Proyecto: Dojo Número Uno.
![image](https://user-images.githubusercontent.com/123998550/233519462-744e405f-5e5a-4136-8178-43d69261f055.png)
## Descripción
El gobierno de la cuidad quiere actualizar los semáforos que tiene instalados. Por lo tanto, en el proyecto presentamos un semaforo funcional con 6 leds y un buzzer que cumple con la función de indicarle a las personas no videntes en que color están encendidas las led del semáforo.

**Para personas videntes:**

- Se enciende el led rojo durante 30 segundos.
- Se enciende el led amarillo durante 5 segundos.
- Se enciende el led verde durante 45 segundos.

**Para personas no videntes:**

- Durante el led rojo, la bocina sonará una vez por segundo durante 30 segundos.
- Durante el led amarillo, la bocina sonará una vez cada dos segundos durante 5 segundos.
- Durante el led verde, la bocina no sonará.

## Funcion principal
~~~ C (lenguaje en el que esta escrito)
void ejecutar_proceso()
{
  encender_led(LED_ROJO, 0);
  encender_buzzer(500, 30, 1000); 
  apagar_led(LED_ROJO, 0.75);
  encender_led(LED_AMARILLO, 0); 
  encender_buzzer(1500, 2, 2500); 
  apagar_led(LED_AMARILLO, 0.75);
  encender_led(LED_VERDE, 45); 
  apagar_led(LED_VERDE, 0.75);
  encender_led(LED_AMARILLO, 0);
  encender_buzzer(1500, 2, 2500); 
  apagar_led(LED_AMARILLO, 0.75);
}
~~~
"ejecutar_proceso" Es la función principal del código. Esta función engloba otras 3 funciones, las cuales se encargan de:
- Encender las luces led.
~~~ C (lenguaje en el que esta escrito)
void encender_led(int led_recibido, int pausa_recibida)
{
  digitalWrite(led_recibido, HIGH);
  pausa_recibida = pausa_recibida * 1000;
  delay(pausa_recibida);
}
~~~
- Apagar las luces led.
~~~ C (lenguaje en el que esta escrito)
void apagar_led(int led_recibido, float pausa_recibida)
{
  digitalWrite(led_recibido, LOW);
  pausa_recibida = pausa_recibida * 1000;
  delay(pausa_recibida);
}
~~~
- Encender el buzzer.
~~~ C (lenguaje en el que esta escrito)
void encender_buzzer(int frecuencia_recibida, int vueltas_recibidas, int pausa_recibida)
{
  contador = 0;
  while (contador < vueltas_recibidas)
  {
    tone(BUZZER, frecuencia_recibida, 500);
    delay (pausa_recibida);
    contador += 1;
  }
}
~~~
## Link del proyecto
- [Proyecto](https://www.tinkercad.com/things/h1WbVGTJFAf)
## Fuentes
- [Formato para hacer el readme](https://github.com/Estebamq/EjemploDocumentacion/blob/main/README.md)
- [Como aprendimos a conectar el buzzer](https://www.tinkercad.com/things/bBK1SUiRnVm-buzzer)
- [Sintaxis para documentar](https://docs.github.com/es/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Tutorial para usar markdown](https://www.youtube.com/watch?v=oxaH9CFpeEE&ab_channel=FaztCode)


