# MARYUM-ASIF-68938-OOP-LAB-TASKS-
TASK 1:
abstract class Vehicle {
    abstract void start();  }
class Car extends Vehicle {
    private String model;
    Car(String model) {
        this.model = model;
    }
    void start() {
        System.out.println("The car " + model + " is starting...");
    }
}
class Motorcycle extends Vehicle {
    private String brand;
    Motorcycle(String brand) {
        this.brand = brand;
    }
    void start() {
        System.out.println("The motorcycle " + brand + " is starting...");
    }
}
public class Main {
    public static void main(String[] args) {
        Vehicle car = new Car("Toyota Corolla");
        Vehicle bike = new Motorcycle("Honda");

        car.start();
        bike.start();    }
}
TASK 2:
abstract class Seat {
    abstract int calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException;
}
class BusinessClass extends Seat {
    private int pricePerSeat = 5000;

    int calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException {
        if (numberOfSeats <= 0) {
            throw new IllegalArgumentException("Number of seats must be greater than 0.");
        }
        return numberOfSeats * pricePerSeat;
    }
}

class FirstClass extends Seat {
    private int pricePerSeat = 8000;

    int calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException {
        if (numberOfSeats <= 0) {
            throw new IllegalArgumentException("Number of seats must be greater than 0.");
        }
        return numberOfSeats * pricePerSeat;
    }
}

class EconomyClass extends Seat {
    private int pricePerSeat = 3000;

    int calculateSeatPrice(int numberOfSeats) throws IllegalArgumentException {
        if (numberOfSeats <= 0) {
            throw new IllegalArgumentException("Number of seats must be greater than 0.");
        }
        return numberOfSeats * pricePerSeat;
    }
}

public class AirlineTicketSystem {
    public static void main(String[] args) {

        try {
            Seat business = new BusinessClass();
            Seat first = new FirstClass();
            Seat economy = new EconomyClass();

            System.out.println("Business Class Price: " + business.calculateSeatPrice(3));
            System.out.println("First Class Price: " + first.calculateSeatPrice(2));
            System.out.println("Economy Class Price: " + economy.calculateSeatPrice(5));

        } catch (IllegalArgumentException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

