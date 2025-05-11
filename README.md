### Hi, i'm Gwen Urbina![GitHub](https://github.blog/wp-content/uploads/2024/05/GitHub-for-beginners.png?fit=1600%2C840 "GitHub")
<p>
utilización de comandos GitHub;
</p>>

- git config --global user.name "Wen"
- git config --global user.email "wenucha52gmail.com"
<p>
Registro de usuario GitHub
</p>>

- git init
- git status
- git add .
- git commit
- git push

####Codigos de programación de cantidades de la población

using System.Collections;
//programa que permita visualizar los depatarmentos de Nicaragua con
//cantidad poblacional.
//Encuentre: Mayor, menor, sumas y ordene los datos
Dictionary<string, int> dep = new()
{
    {"Boaco",185013},
    {"Carazo",197139},
    {"Chinandega",439906},
    {"Chontales",190863},
    {"Costa Caribe Norte",530586},
    {"Costa Caribe Sur",414543},
    {"Estelí",229866},
    {"Granada",214317},
    {"Jinotega",475630},
    {"León",421050},
    {"Madriz",174744},
    {"Managua",1,575,819},
    {"Masaya",391903},
    {"Matagalpa",593503},
    {"Nueva Segovia",271581},
    {"Río San Juan",135446},
    {"Rivas",182645}
};
//Ordenando con diccionario y Orderby de LINQ
var orderDepResult = dep.OrderBy(d => d.Value);
//Encontrar el menor
var menDep = dep.Select(d => d).Where(d => d.Value == dep.Values.ToArray().Min());
Console.WriteLine("Departamento con menor Población:");

foreach (var order in menDep)
//Encontar el depatarmento con mayor población
    Console.WriteLine($"{order.Key,20} ==> {order.Value,10:N0}");
Console.WriteLine("Departamento con mayor Población:");
foreach (var item in orderDepResult)
    Console.WriteLine($"{item.Key,20} ==> {item.Value,10:N0}");
//Sumar todas la poblaciones con LINQ
int total = orderDepResult.ToDictionary(kvp => kvp.Key, kvp => kvp.Value).Values.ToArray().Sum();

Console.WriteLine($"Población General:{total,17:N0}");
//Mostrar los tres departamentos con mayor población 
var tresMayores = orderDepResult.TakeLast(3);
Console.WriteLine($"Los tres departemento con mayor población son:");
tresMayores = tresMayores.OrderByDescending(d => d.Value);
foreach (var item in tresMayores)
    Console.WriteLine($"{item.Key}");


