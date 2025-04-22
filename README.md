SOLID Principles Project
This project is a basic demonstration of the SOLID principles with practical examples in Java.
Each principle is illustrated with specific classes, organized into folders.

Project Structure
The project is organized into folders, each representing one of the SOLID principles.
Below is the list of folders and the associated classes, each with an explanation of the principle and its application.

SRP (Single Responsibility Principle)
A class should have only one reason to change, one single responsibility.
In this project, the Pedido class handles only order calculation, while the Recibo class handles the generation and printing of the receipt.

Folder: SRP

Principle Application:

The Pedido class has only one responsibility: managing the order items and calculating the total value.

The Recibo class has only one responsibility: generating and printing the receipt.

This makes the code easier to maintain and test.

Principle Violation:

In the violation, the PedidoSemSRP class does two things: calculates the order total and prints the receipt.
This makes the code harder to maintain and reuse.

OCP (Open/Closed Principle)
A class should be open for extension but closed for modification.
In this project, the Calculadora class is open for extension because it can calculate the area of different shapes, as long as the new shape implements the Forma interface.
The Calculadora class is closed for modification because there's no need to change its code to add a new shape.

Folder: OCP

Principle Application:

The Desconto interface defines a contract for applying discounts.

Classes like DescontoNatal and DescontoBlackFriday implement the Desconto interface.

The CalculadoraDesconto class can calculate discounts for any Desconto implementation without needing to be modified.

Principle Violation:

In the violation, the CalculadoraDescontoSemOCP class must be modified every time a new type of discount is added,
because it uses conditions (if-else) to check the discount type.

LSP (Liskov Substitution Principle)
Objects of a derived class should be able to replace objects of the base class without altering the behavior of the program.
In this project, Quadrado and Retangulo implement the Forma interface without violating the expected behavior.

Folder: LSP

Principle Application:

The Forma interface defines a contract to calculate the area.

Classes like Retangulo and Quadrado implement the Forma interface independently.

This ensures that Quadrado and Retangulo can be used interchangeably without causing unexpected behavior.

Principle Violation:

In the violation, QuadradoSemLSP inherits from RetanguloSemLSP and changes the behavior by modifying both sides when setting the width or height.
This breaks substitution because a Quadrado cannot be used as a Retangulo without causing issues.

ISP (Interface Segregation Principle)
A class should not be forced to implement methods it does not use.
In this project, the Trabalhador interface is separated from the Comer interface, allowing Robo to implement only Trabalhador.

Folder: ISP

Principle Application:

The Trabalhador interface defines only the work method.

The Comer interface defines only the eat method.

Classes like Humano implement both interfaces, while Robo implements only Trabalhador.

This avoids forcing Robo to implement methods it doesn’t need.

Principle Violation:

In the violation, the TrabalhadorSemISP interface forces the RoboSemISP class to implement the eat method, even though it doesn’t make sense for robots.
This results in unnecessary and potentially problematic implementation.

DIP (Dependency Inversion Principle)
High-level modules should not depend on low-level modules. Both should depend on abstractions.
In this project, the Notificacao class depends on the MensagemService abstraction, allowing any messaging service to be injected.

Folder: DIP

Principle Application:

The MensagemService interface defines a contract to send messages.

Classes like EmailService and SMSService implement the MensagemService interface.

The Notificacao class depends on the MensagemService abstraction, allowing any messaging service to be injected without modifying Notificacao.

Principle Violation:

In the violation, the NotificacaoSemDIP class depends directly on EmailServiceSemDIP, a concrete implementation.
This makes it hard to replace with another messaging service like SMS without modifying the code of NotificacaoSemDIP.
