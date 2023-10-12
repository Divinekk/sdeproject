-- Create the Cars table
CREATE TABLE Cars (
    car_id NUMBER PRIMARY KEY,
    model CHAR(255),
    year NUMBER,
    brand CHAR(255),
    color CHAR(255),
    dailyrate NUMBER(10, 2)
);

-- Create the Customers table
CREATE TABLE Customers (
    customer_id NUMBER PRIMARY KEY,
    first_name CHAR(255),
    last_name CHAR(255),
    license_number CHAR(20)
);

-- Create the Rentals table
CREATE TABLE Rentals (
    rental_id NUMBER PRIMARY KEY,
    customer_id NUMBER,
    car_id NUMBER,
    rental_date DATE,
    final_price NUMBER(10, 2),
    FOREIGN KEY (customer_id) REFERENCES Customers(customer_id),
    FOREIGN KEY (car_id) REFERENCES Cars(car_id)
);
