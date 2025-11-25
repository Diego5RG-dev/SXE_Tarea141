# SXE_Tarea14

---
Preparación
---

Para esta actividad tendremos que crear un servicio de Odoo desde cero, así que reutilizaremos el código del Docker Compose que ya teníamos en tareas anteriores.

![alt text](https://github.com/Diego5RG-dev/SXE_Tarea141/blob/main/recursosOdoo/1.png)


Tenemos que acordarnos de incluir los datos demo para la base de datos.

---
Actividad 1
---

En esta actividad, generaremos una nueva tabla que cumpla con los requisitos especificados en la tarea. Esta será una tabla de empresa con diferentes columnas. Para lograrlo, simplemente tenemos que crear la tabla directamente en pgAdmin, el cual ya está conectado a la base de datos de Odoo.

![alt text](https://github.com/Diego5RG-dev/SXE_Tarea141/blob/main/recursosOdoo/2.png)


---
Actividad 2 
---

Ahora, para que esta no quede vacía, lo que haremos será insertar datos en la tabla y en sus correspondientes columnas mediante una sentencia INSERT simple.

![alt text](https://github.com/Diego5RG-dev/SXE_Tarea141/blob/main/recursosOdoo/3.png)


    INSERT INTO public."EmpresasFCT"(
    "nombre", "quiereAlumnos", "numAlumnos", "fechaContacto")
     VALUES ('Amazon', FALSE, 20, '2001-12-07'),
     ('Aliexpress', TRUE, 12, '2002-10-04'),												
     ('neflix', FALSE, 13, '2012-05-28'),
     ('HBO', TRUE, 45, '2005-09-22'),
     ('Disney', FALSE, 32, '2011-02-04');

  ![alt text](https://github.com/Diego5RG-dev/SXE_Tarea141/blob/main/recursosOdoo/4.png)


---
Actividad 3
---

Ahora, procederemos a ejecutar una sentencia SELECT para visualizar todos los datos en la tabla, aplicando la condición de ordenamiento (ORDER BY) requerida por el ejercicio.

    SELECT * FROM public."EmpresasFCT" ORDER BY "fechaContacto" DESC;

  ![alt text](https://github.com/Diego5RG-dev/SXE_Tarea141/blob/main/recursosOdoo/5.png)


---
Actividad 4
---

Tenemos que ejecutar una consulta para visualizar los datos de Odoo. Básicamente, se trata de replicar el proceso anterior, pero aplicándolo a toda la base de datos de Odoo.

    SELECT name as nombre ,commercial_company_name as nombre_empresa FROM public.res_partner
     WHERE is_company = false and city != 'Tracy' ORDER BY commercial_company_name;

![alt text](https://github.com/Diego5RG-dev/SXE_Tarea141/blob/main/recursosOdoo/6.png)


---
Actividad 5 y 6 
---

Actividad en pausa debido a errores


---
Actividad 7
---

Crear una sentencia UPDATE para actualizar el correo electrónico de un registro específico.

![alt text](https://github.com/Diego5RG-dev/SXE_Tarea141/blob/main/recursosOdoo/9.png)

        UPDATE public.res_partner SET email = REPLACE(email,'example.com','bizkaia.eus')
         WHERE email like '%@bilbao.example.com'
