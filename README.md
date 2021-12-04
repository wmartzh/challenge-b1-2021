# Backend Winter Challenge 2021


# Descripción del Proyecto

En el presente proyecto se busca crear una aplicación para el manejo de finanzas personales y como backend se requiere crear una API que manejara toda la lógica de negocios de la aplicación, desde el manejo de los usuarios hasta la generación de reportes por lo que se establecen ciertos requerimientos para la realización del backend.

La aplicación tiene como objetivo prestar una herramienta para que cualquier persona pueda llevar el control de ingresos y gastos dentro de la aplicación además de la administración de presupuestos y administración de saldos bancarios dentro de la aplicación.


# Especificación de Requerimientos


## Usuarios

Los usuarios podrán registrarse en cualquier momento con su información personal y los datos de autenticación, por otro lado, la aplicación reconocerá dos tipos de usuarios - clientes y administradores los cuales se definen como:

- **Clientes:Son los clientes de la aplicación y los que utilizaran la aplicación con las diferentes características**
- **Administradores:Los administradores se encargarán de administrar todos los usuarios de la plataforma y las diferentes membresías**

| **Requerimientos**   | **Descripción**                                                            | **Indispensable tener**                                                                                                                                                                                          | **No indispensable tener**                                                 |
| -------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Registrar Usuario    | Como persona podre crear una cuenta en la plataforma para ser un cliente.  | - Información Personal: nombre, correo, contraseña como mínimo - Establecer una membresía gratuita por defecto - Utilización un método de para la encriptación de la contraseña con la utilización de un hash    |                                                                            |
| Editar información   | Como cliente podre editar mi información personal y restablecer contraseña | - Cambio de toda la información personal                                                                                                                                                                         | - Cambiar membresía - Cambio de datos de autenticación (correo/contraseña) |
| Administrar usuarios | Como administradora podre acceder a la información de todos los usuarios   | - Crear usuarios nuevos - Editar - Eliminar usuarios                                                                                                                                                             | - Generación de contraseñas                                                |


## Autenticación

El acceso a las diferentes características estará determinada por el tipo de usuario y la membresía que este adquiera, la API deberá utilizar un sistema de autenticación para la habilitación de cada uno de los recursos a esta.

[![](https://lh4.googleusercontent.com/hd_blutYsucsKih6LEKveH2Axp6BiYEiTSAEakZfUlx2V6Bvn5PU3H_Xah1cEdNlPu2ZBwmkdJ16Xmyvbylpx3Qh3nLrjP6LyZLEdNJsfNaxuErrzMacUyWm5dVvHoIO7H_WC7T4)](https://lucid.app/documents/edit/af4b65a5-0c92-4247-a8b5-55a8e0ca0a40/1?callback=close&name=docs&callback_type=back&v=1137&s=658)

| **Requerimientos**              | **Descripción**                                                                                          | **Indispensable tener**                                                                                                                                      | **No indispensable tener** |
| ------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------- |
| Inicio de sesión                | Como usuario, podre acceder a la aplicación para utilizar las herramientas de acuerdo al tipo de usuario | - Validación de datos del usuario - Manejo de errores - Recuperación de contraseña                                                                           |                            |
| Validación de acceso a recursos | El acceso a los recursos dependerán al los permitidos                                                    | - Validar tipo de usuario al acceso a los recursos - Validar si la membresía permite el acceso al recurso con usuarios, esto no aplica a los administradores |                            |


## 


## Membresías

Todos los usuarios podrán tener un plan prémium el cual habilitara a los usuarios (clientes) acceso a características que los que no lo han obtenido no, los cuales se definen como:

- **Plan Gratuito:Este es el plan por defecto que todo usuario podrá tener al momento de registrarse y dará acceso a las siguientes características**

  - Administración de Presupuestos
  - Administración de Ingresos y Gastos
  - Reportes de Ingresos y Gastos

- **Plan Prémium:Este plan tendrán acceso a aquellos que lo adquieran y tendrán acceso a las siguientes características**

  - Administración de Presupuestos
  - Administración de Ingresos y Gastos
  - Control de Saldos
  - Presupuestos diarios
  - Reportes de Ingresos y Gastos

| **Requerimientos**        | **Descripción**                                                                 | **Indispensable tener**                                   | **No indispensable tener**         |
| ------------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------- | ---------------------------------- |
| Control de autorizaciones | Como clientes podrán acceder a las características según lo defina la membresía | - Los usuarios deberán estar asociados a una membresía    | - Simulación de pagos de membresía |


## Presupuestos

Un presupuesto es una delimitación de dineros establecidos para un fin en específico antes de ejecutar esta. En términos de finanzas personales estos pueden estar establecidos por proyectos que una persona se proponga cumplir para ello un presupuesto puede tener diferentes categorías el cual conforme se vayan realizando gastos el monto del presupuesto restante son los gastos realizados en esa categoría menos el presupuesto asignado para la misma.

  
[![](https://lh3.googleusercontent.com/rRlAZ8SaYXCk7qILFbPhf8EUCcsGG0P_NaTW02lpR6wRljIUlMtiPMBfTYlB607nA7UDOcZEMQmIFgX8ZvTBZQPQLGbk7ZdajIUrmNBnWDttXD-EQ-YXdXj-GSKeRbMV67W1uduh)](https://lucid.app/documents/edit/af4b65a5-0c92-4247-a8b5-55a8e0ca0a40/2?callback=close&name=docs&callback_type=back&v=1137&s=612)

| **Requerimientos**    | **Descripción**                                                                | **Indispensable tener**                                                                                                                                                         | **No indispensable tener** |
| --------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| Crear Proyectos       | Los clientes podrán crear diferentes proyectos para la creación de presupuesto | - Establecer un nombre y descripción por proyecto creado                                                                                                                        |                            |
| Ver Proyectos         | El cliente podrá ver todos los proyectos creados por sí mismo                  | - Filtrar por fecha de forma ascendente y descendente - Realizar paginación de 10 registros por página.                                                                         |                            |
| Editar Proyectos      | El cliente podrá editar sus proyectos                                          | - Solo podrá editarse la información personal                                                                                                                                   |                            |
| Eliminar Proyectos    | El cliente podrá eliminar los proyectos que le pertenece.                      | - Al eliminar un proyecto automáticamente se eliminarán todos los datos relacionados con el proyecto                                                                            |                            |
| Ver categorías        | Se podrán listar las categorías                                                | - Filtrar por tipo - Realizar paginación de 10 registros por página.                                                                                                            |                            |
| Crear Categorías      | Para la creación del presupuesto es necesario crear categorías                 | - Establecer si la categoría es un ingreso o un gasto                                                                                                                           |                            |
| Crear Presupuesto     | El usuario podrá establecer diferentes montos por categoría                    | - El presupuesto deberá tener al menos una categoría de ingreso o gasto - Establecer un nombre y deberá estar asociado al menos a un proyecto - Definir un periodo de ejecucion |                            |
|    Editar presupuesto | Se podrá editar un presupuesto                                                 | - Editar montos - Añadir o editar categorías - Editar el nombre y la descripción                                                                                                |                            |


## Ingresos y Gastos

Los usuarios podrán ingresar transacciones que representan ingresos o gastos de acuerdo a las categorías establecidas dentro del presupuesto

| **Requerimientos**                    | **Descripción**                                                                | **Indispensable tener**                                                                                                                                                                                         | **No indispensable tener** |
| ------------------------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| Registro de ingresos o gasto          | El usuario podrá realizar el ingreso de sus ingresos o gastos                  | - Ingreso de montos, u fecha del ingreso(Esta fecha sería definida de forma automática por el sistema) - Estas transacciones deberán estar asociadas a las diferentes categorías establecidas en el presupuesto |                            |
| Editar Ingreso o Gasto                | Los usuarios podrán editar los montos de los ingresos y gastos ya registrados. | - Únicamente se podrán editar los montos de los ingresos o gastos - Deberá registrarse si el ingreso o el gasto fue editado                                                                                     |                            |
| Ver Ingresos y Gastos                 | Se podrá ver el listado de los ingresos y gastos que el usuario haya ingresado | - Filtrar por fecha y por tipo - Realizar paginación de 10 registros por página.                                                                                                                                |                            |
| Descargar reporte de ingreso o gastos | El usuario podrá descargar un Excel donde se muestren los ingresos o gastos    | - Filtrar por fechas y tipo (Ingreso o gasto)                                                                                                                                                                   |                            |


## Presupuesto Diario

Según las categorías creadas en los presupuestos se podrá consultar el presupuesto diario para cada categoría con base a los gastos, el sistema podrá determinar cuál es el monto restante para esa categoría, Por ejemplo, se asignan $200 para la categoría “comida” y a medio mes se gastó la mitad, por lo que el presupuesto diario son $6,66 diarios para alcanzar el presupuesto de $200.

| **Requerimientos**                               | **Descripción**                                                      | **Indispensable tener**                                                                             | **No indispensable tener** |
| ------------------------------------------------ | -------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | -------------------------- |
| Obtener el presupuesto diario para una categoría | Obtener el presupuesto diario a gastar a la fecha dada una categoría | - Consular por categoría - Consultar por fecha especifica en el futuro - Consultar en el día actual |                            |


# API

La API deberá tener los siguientes endpoints de acuerdo a los requerimientos establecidos:

| **Endpoint**   | **Metodos Admitidos**     |
| -------------- | ------------------------- |
| /auth/registro | POST                      |
| /auth/login    | POST                      |
| /usuarios      | GET, POST, UPDATE, DELETE |
| /membresias    | GET, POST                 |
| /proyectos     | GET, POST, UPDATE, DELETE |
| /presupuestos  | GET, POST, UPDATE, DELETE |
| /categorias    | GET, POST, UPDATE, DELETE |
| /transacciones | GET, POST, UPDATE         |
| /reportes      | GET                       |

	💡 NOTA: Podrán ser agregadas las diferentes sub rutas si es necesario

# Desarrollo

El desarrollo se podra realizar en el stack que el desarrollador mas prefiera, sin embargo se da la siguiente recomendacion:

 - [ExpressJS](https://expressjs.com/)
 - [Prisma](https://www.prisma.io/)

## Sub Challenge
Realiza la implemetacion de la documentacion en [swagger](https://swagger.io/) si se esta utilizando Node o Python
