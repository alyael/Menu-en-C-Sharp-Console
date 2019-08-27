﻿# Menu-en-C-Sharp-Console
 
 <p>
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace clasePromedio
{
    class clasePromedio
    {

        //declaración de variables de la clase
        private static string matricula, nomAlum;
        private static int numCalif, opcion = 0;
        private static float suma, calif, promedio;
        private static bool entro1, entro2, entro3;

        static void Main(string[] args)
        {

            //llamada al menú de opciones
            imprimirMenu();

        }


        //impresion del menú de opciones
        private static void imprimirMenu()
        {

            Console.Clear();
            Console.WriteLine("--IMPRIMIENDO MENU--\n");
            Console.WriteLine("1. LECTURA DE DATOS");
            Console.WriteLine("2. CALCULO DE PROMEDIO");
            Console.WriteLine("3. MOSTRAR DATOS");
            Console.WriteLine("4. SALIR\n");
            Console.Write("Elige una opción: ");
            int opcion = int.Parse(Console.ReadLine());
            do
            {
                switch (opcion)
                {

                    case 1:
                        if (entro1 == false)
                        {
                            entradaDatos();
                            entro1 = true;
                            entro2 = false;
                            entro3 = false;
                            imprimirMenu();
                        }
                        else
                        {
                            Console.WriteLine("********Ya se hizo la LECTURA DE DATOS********");
                            Console.ReadKey();
                            imprimirMenu();
                        }
                        break;

                    case 2:
                        if (entro2 == false)
                        {
                            calculoPromedio();
                            entro2 = true;
                            imprimirMenu();
                        }
                        else
                        {
                            Console.WriteLine("********Ya se hizo el CALCULO DE PROMEDIOS********");
                            Console.ReadKey();
                        }
                        break;


                    case 3:
                        if (entro3 == false)
                        {

                            mostrarDatos(nomAlum, matricula, promedio);
                            entro3 = true;
                            imprimirMenu();
                        }
                        else
                        {
                         
                            Console.WriteLine("********Ya se IMPRIMIERON LOS RESULTADOS********");
                            Console.WriteLine("****************SALIR DEL SISTEMA***************");
                            Console.ReadKey();
                        }
                        break;

                    case 4:
                        Console.Clear();
                        Console.WriteLine("----FIN DEL PROGRAMA----");
                        Console.ReadKey();
                        break;

                    default:
                        Console.WriteLine("----OPCION INCORRECTA----");
                        Console.ReadKey();
                        imprimirMenu();
                        break;
                }

            }
            while (opcion > 4);
            Console.ReadKey();
        }


        //lectura de datos del alumno
        private static void entradaDatos()
        {
            Console.Clear();
            Console.WriteLine("--INTRODUCIENDO DATOS--\n");
            Console.Write("Introduce Matricula: ");
            matricula = Console.ReadLine();
            //ToUpper permite convertir una cadena de caracteres a MAYUSCULAS
            matricula.ToUpper();
            Console.Write("Introduce Nombre completo: ");
            nomAlum = Console.ReadLine();
            nomAlum = nomAlum.ToUpper();
            Console.Write("Número de calificaciones a capturar: ");
            numCalif = int.Parse(Console.ReadLine());

        }

        
        //lectura de calificaciones y cálculo del promedio
        //retorna el promedio del alumno
        private static void calculoPromedio()
        {

         
            Console.WriteLine("--INTRODUCIENDO CALIFICACIONES--\n");
             
            for (int i=1; i <= numCalif; i++) { 
                Console.Write("Introduce la calificación " + i + ": ");
                calif = float.Parse(Console.ReadLine());
                suma = suma + calif;
            }

            promedio = suma / numCalif;

        }
        

        //impresión de resultados del alumno
        private static void mostrarDatos(string nomAlum, string matricula, float promedio)
        {
        
            Console.WriteLine("--IMPRIMIENDO DATOS--\n");
            Console.WriteLine("Alumno: " + nomAlum);
            Console.WriteLine("Matricula: " + matricula);
            Console.WriteLine("Promedio final: " + promedio);
            Console.ReadKey();

        }
        


    }
}
</p>
