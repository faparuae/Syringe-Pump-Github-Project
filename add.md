- [Home](/Syringe-Pump-Github-Project/index)
- [Mechanical](/Syringe-Pump-Github-Project/MechanicalAssembly)
- [Electrical](/Syringe-Pump-Github-Project/Electrical)
- [Code](/Syringe-Pump-Github-Project/code)
- **[Additional Factors](/Syringe-Pump-Github-Project/add)**

# Additional Factors to Consider

### How many steps per mL? 
Typically, a stepper motor takes 200 steps per rotation. However, with microstepping, the stepper motor can take 1/16 of the original step size. Therefore, with microstepping, a stepper motor could take 3,200 steps per rotation. 

Pitch is the distance between screw grooves, and the pitch of the screw used in the syringe pump is 1.25 mm. This means that, linearly, there is 1.25 mm of movement for  every rotation of the screw. Finally, the smallest height we could have for each step within our motor would be pitch divided by the steps per rotation. In this case, that would be (1.25)/3200 = 0.00039 mm. 

Working backwards, we can find out how many steps the motor takes per 1 mL. Volume is equal to height x area. The height will tell us how many steps, and the area is already known. In this case, the area is pi* r^2. The radius of the syringe is 9.5 mm, or 0.95 cm, so the area is 2.84 cm2. 

With the area, we can now find the height associated with a volume 1 mL = 1 cm3: 

height = z = Volume/Area = 1 cm3/2.83 cm2 --> z = 0.352 cm. 

We know that the pitch of the screw is 1.25 mm, or 0.125 cm, 

so: 0.125 cm per rotation/number of steps per rotation = 0.352 cm --> Number of steps = 0.125 cm/0.352 cm

Number of steps per mL = 0.355 

**In conclusion, the motor takes 0.355 steps to expel 1 mL of fluid.** 

### What is the resolution? 
On the same basis of the earlier calculation for steps per mL, we can also find the resolution. The resolution is 1 mL divided by the number of steps calculated. In this case, the resolution is 1 mL/0.355 = 2.82 cm3.  
**So the resolution would be 2.82 mL.**

### What is the limiting factor on the maximum flow rate?  
700 rpm is the maximum amount of turns that the motor can perform before the torque gives out. However, the actual value that the motor will spin is less than that due to friction between the nut and bolt. 
