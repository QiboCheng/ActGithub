import java.time.Duration;
import java.time.LocalTime;
import java.util.Scanner;

public class Ejercicio1 {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("¿A que hora empiezas a estudiar?");
        String primera = sc.nextLine();
        LocalTime Inicio = LocalTime.parse(primera);

        System.out.println("¿A que hora terminas de estudiar?");
        String segunda = sc.nextLine();
        LocalTime Fin = LocalTime.parse(segunda);

        long CalcularSegundos = CalcularDifSegundos(Inicio, Fin);

        long horas = CalcularSegundos / 3600;
        long minutos = (CalcularSegundos % 3600) / 60;
        long segundos = CalcularSegundos % 60;

        System.out.printf("Has estudiado %d horas %d minutos %d segundos.%n", horas, minutos, segundos);

    }

    public static long CalcularDifSegundos(LocalTime HoraInicio, LocalTime HoraFin){

        Duration duracion = Duration.between(HoraInicio, HoraFin);
        return duracion.getSeconds();

    }
}
