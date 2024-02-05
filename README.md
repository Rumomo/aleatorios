(Ev). Actividad: Debuggin y puntos de ruptura. Números aleatorios
El código que se adjunta a continuación tiene por objetivo visualizar números de forma aleatoria.
"El siguiente código en Java tiene un error que impide la generación correcta de números aleatorios. 
Tu tarea es identificar y corregir el error para que el programa genere correctamente un array de números aleatorios. 
Utiliza el método Math.random() para generar números aleatorios entre 0 y 1, y luego multiplícalos por 100 para obtener valores en el rango de 0 a 100. 
Asegúrate de que el programa solicite al usuario la cantidad de elementos deseados y luego imprima el array generado. ¡Buena suerte!"

Para evaluar la actividad encuentra el fallo y entrega el código arreglado, aquí: 
package aleatorios;
import javax.swing.JOptionPane;

public class aleatorios {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int elementos=Integer.parseInt(JOptionPane.showInputDialog("Teclea un numero + de uno=>"));
		int num_aleat[]=new int[elementos];
		for (int i=0; i< num_aleat.length;i++) {
			num_aleat[i]=(int)Math.random()*100;
		}
		for (int elem: num_aleat) {
			System.out.println(elem);
		}

	}

}
Recuerda subir a github

Para empezar ponemos un punto de ruptura en el bucle for:
![image](https://github.com/Rumomo/aleatorios/assets/26388833/97c8ea25-7583-48c8-a25a-39fda85cf3f1)
Cuando entramos dentro del bucle, tenemos la sentencia siguiente: 
**num_aleat[i]=(int)Math.random()*100;** 
Esta sentencia lo que intenta hacer es meter en el array en la posición de i, un número aleatorio de la clase Math. La función random,
genera números aleatorios pero decimales, por debajo del 0 hasta 100. Que ocurre en esta parte, al no estar bien encasulado. Ya que hara primero el
casteo a número entero y por separado el math. random y solo se guardán los 0 ya que nunca los termina de convertir
![Captura de pantalla 2024-02-05 114641](https://github.com/Rumomo/aleatorios/assets/26388833/5fcfd2d2-9ccf-4daa-89db-a58ab0db374b)
![Captura de pantalla 2024-02-05 114655](https://github.com/Rumomo/aleatorios/assets/26388833/c1e655ec-49f5-4aaf-b71c-f41ba519b97d)
![Captura de pantalla 2024-02-05 114726](https://github.com/Rumomo/aleatorios/assets/26388833/4f903787-4966-43fe-876b-f8a67825c614)
Para solucionarlo tenemos que encapsular bien las funciones:
**num_aleat[i]=(int)(Math.random()*100);** 
![Captura de pantalla 2024-02-05 114833](https://github.com/Rumomo/aleatorios/assets/26388833/f9f3ff35-b2e6-47d9-9bcf-a7150e3f7a09)
![Captura de pantalla 2024-02-05 114852](https://github.com/Rumomo/aleatorios/assets/26388833/ec265504-ba61-4669-9642-81b7c259d023)
![Captura de pantalla 2024-02-05 114901](https://github.com/Rumomo/aleatorios/assets/26388833/26f8219c-bf9b-48bc-a0fe-d58a8130b55b)




