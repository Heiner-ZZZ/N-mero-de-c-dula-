# N-mero-de-c-dula-
//Programa donde pide al usuario 9 dígitos, y mediante una serie de validaciones de los primeros cuatro números que si se cumplen todos , calcula el décimo digito del numero de cédula
 //ME REGRESO.. 
repetir://si es mayor a 6 
 regresarse://si tiene menos o mas de 9 digitos
 pArriba://si su suma de los dos primeros dijitos no cumple
 Console.WriteLine("Ingrese un numero hasta el penultimo digito");
 string pedirC = Console.ReadLine();
 if (pedirC.Length != 9)
 {
 Console.WriteLine("INGRESE UN NUMERO DE 9 DIJITOS");
 goto regresarse;
 }
 if (pedirC[2] >= '6')//verifico que no sea mayor a 6
 {
 Console.WriteLine("el numero en la pocicion 3 -- {0}", pedirC[2]);
 Console.WriteLine("----Debe ser menor que 6---");
 goto repetir;
 }
 int[] posic2 = new int[2];
 posic2[0] = int.Parse(char.ToString(pedirC[0]));
 posic2[1] = int.Parse(char.ToString(pedirC[1]));
 if (posic2[0] >= 2 )
 {
 if ( posic2[1] > 4)
 {
 goto pArriba;
 }
 }
 int[] impar = new int[5];
 int[] pares = new int[4];
 int cont = 0;
 int totImpar = 0;
 for (int i = 0; i < 9 ; i=i+2 )
 {
 impar[cont] = pedirC[i] - '0';//al restar el valor de ‘0’ se obtiene el num real
 impar[cont] = impar[cont] * 2;
 if (impar[cont] >=10 )//si se pasa de 10 le - 9
 {
 impar[cont] = impar[cont] - 9;
UNIVERSIDAD TÉCNICA ESTATAL DE QUEVEDO
 }
 totImpar = totImpar + impar[cont];//SUMA TOTAL DE IMPARES
 //Console.WriteLine(i+ " impar " +impar[cont] + " ");
 cont++;
 if (i > 8 )
 {
 goto salImpar;
 }
 }
salImpar:
 ////////////////////////////////
 int cont2 = 0;//segundo contador
 int totPar = 0;
 for (int i = 1; i < 9; i=i+2 )
 {

 pares[cont2] = pedirC[i] - '0';//al restar el valor de ‘0’ se obtiene el num real
 totPar = totPar + pares[cont2];
 // Console.WriteLine(cont2 + "--par " + pares[cont2] + " ");
 cont2++;
 if (i > 7 )
 {
 goto salpar;
 }
 }
salpar:
 int TOTALGOD;
 TOTALGOD = totImpar + totPar;
 if (totImpar % 10 == 0)
 {
 Console.WriteLine();
 Console.WriteLine("su ultimo digito es 0");
 Console.WriteLine("N.C {0}-0", pedirC);
 }
 else
 {
 Console.WriteLine();
 Console.WriteLine("su ultimo digito es {0}", 10 - (TOTALGOD % 10));
 Console.WriteLine("N.C {0}-{1}", pedirC, 10 - (TOTALGOD % 10));
 }
 Console.ReadKey();
