import java.util.Scanner; 

public class SimpleCar { 

	public String color; 
	public String make; 
	public String model; 
	public boolean isCarStarted = false; 
	public int speed = 0; 
	public int gasLevel = 10; 

	public void startCar() {
		System.out.println("Starting your car!"); 
		if (make.equals("Range Rover")) {
			System.out.println("Your Range Rover  is broken - go to your repair shop!"); 
		} else { 
			isCarStarted = true;  
		}
	}

	public void stopCar() {
		System.out.println("Stop car to pick up a girls!"); 
		if (make.equals("Range Rover")) {
			System.out.println("Your Range Rover is broken (again!) - go pay your repair another $10,000 ."); 
		} else { 
			isCarStarted = true;  
		}
	}

	public void accelerate()throws Exception{ 
      

       if(make.equals("Range Rover")) { 
				System.out.println("Sorry! The Range Rover does not get to accelerate"); 
			}


		if (isCarStarted && gasLevel > 0) { 
			speed = speed + 5; 
		} else { 
			throw new Exception("You cannot accelerate your car before you start it."); 
		}
	}

     public void manuallyAccelerate()throws Exception{
        System.out.println("Enter the amount of speed that you want to accelerate your car."); 
      

        Scanner lineScannerManualSpeed= new Scanner(System.in);
        String manualSpeed = lineScannerManualSpeed.nextLine();

        int speedManual =Integer.parseInt(manualSpeed);



       if(make.equals("Range Rover")) { 
				System.out.println("Sorry! The Range Rover does not get to accelerate"); 
			}


		if (isCarStarted && gasLevel > 0) { 
			speed = speed + speedManual; 
		} else { 
			throw new Exception("You cannot accelerate your car before you start it."); 
		}
	}


	 public void brake ()throws Exception  { 
       if(make.equals("Range Rover")) { 
				System.out.println("Sorry! The Range Rover does not get to brake."); 
			}


		if (isCarStarted && gasLevel > 0) { 
			speed = speed - 1; 
		} else { 
			throw new Exception("You cannot brake your car before you start it."); 
		}
	}




    public void fuelUp()throws Exception{ 
     if (make.equals("Range Rover")) { 
				System.out.println("Sorry! The Range Rover has a gas leak."); 
			}


		if (isCarStarted) { 
			gasLevel = gasLevel + 10 ; 
		} else { 
			throw new Exception("You have to start your car before you fuel up on gas."); 
			
		}
	}


	public SimpleCar() { 
		color = " Jerez Black";
		make = "BMW"; 
		model = "m4"; 
	}

	public SimpleCar(String inputColor, String inputMake, String inputModel) {
		color = inputColor; 
		make=inputMake;
		if (make.equals("Toyota")) { 
			make = "Sucky Car"; 
			speed = 50; 
		} else { 
			make = inputMake; 
		}
		model = inputModel;  
	}

   public void printInfo() { 
   System.out.println("You are driving a "+ color + " " + make +" "+ model+".");
   System.out.println("Speed:"+speed + " MPH.");
   System.out.println("Gas level: " + gasLevel + ".");
    
    }
   public void exit() { 
   System.out.println("You just exited your car. ");
   System.out.println("Thank you for test driving with us .");
   System.out.println("Please come back and test drive with us again!!");
    }
