# FASE 1: INVESTIGACIÓN.

Para esta actividad, se nos poide realizar una investigación sobre los nodos de control de UML 2.5, para ello, debemos distinguir entre los rombos y las barras de fork, es decir, decisiones y bifurcaciones.
En UML es  muy importante saber diferenciar entre estos procesos.

## Decisiones (rombo)

El rombo se utiliza cuando el sistema a realizar debe tomar una decisión dependiendo de una condición lógica.
Por ejemplo, si validamos la sesión de un usuario, se debe decidir si la sesión es válida o no lo es

## Bifurcación (barra fork)

La bifurcación se representa mediante una barra negra, a la que llamamos barra fork. Aquí se divide un proceso en vareas que no se ejecutan de forma simultánea

## Join

aquí se sincronizan los procesos de forma simultánea y espera a que todos finalicen antes de continuar

# FASE 2: MODELADO DEL PROCESO DE COMPRA.

<img width="1260" height="1413" alt="confirmaciónPedido" src="https://github.com/user-attachments/assets/f899e569-3c18-440a-93e6-7482e2b48a34" />

Este diagrama de actividad, inicia con la finalización de compra por parte de un usuario. A continuación usamos una barra fork para verificar que hay stock de dicho producto y que el usuario haya iniciado sesión correctamente
Todo ello se realiza de forma independiente.

Una vez finalizadas usamos un join para que se espere a que ambos procesos se hayan completado, ya que no se podría continuar si alguna validación está pendiente.

En este punto comienzan las decisiones. Si las validaciones no han sido exitosas o falla una, se produce un error, dando por finalizado el diagrama de actividad. Si son validads correctamente pasamos a la pasarela de compra.

En la pasarela de compra volvemos a tomar otra decisión, si el pago es fallido, finalizamos el diagrama de actividad, si es existoso, continuamos con una barra fork. donde se deben dar 3 procesos, registrar el pedido en la base de datos, generar un pdf de la compra y confirmar el pedido en el correo electrónico.

Necesitamos que estos 3 procesos se completen para mostrar un mensaje de confirmación, por lo que usamos de nuevo un join y una vez mostrado el mensaje, finalizamos de forma exitosa el diagrama de clase

# WEBGRAFÍA
[1] OMG (Object Management Group), “Unified Modeling Language (UML) Version 2.5,” 2015: https://www.omg.org/spec/UML/

[2] IBM Documentation, “UML activity diagrams,” IBM, 2021: https://www.ibm.com/docs/en/rhapsody/9.0.1?topic=diagrams-uml-activity

[3] Visual Paradigm, “What is Activity Diagram?,” Visual Paradigm: https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-activity-diagram/
