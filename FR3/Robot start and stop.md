
# Emergency stops

- Green
	- Pressed: accepting control commands
	- Unpressed: software-based active breaking to stop
	- Preferred emergency stop for stopping software execution
- Red
	- Pressed: power cut, putting magnetic joint locks in place
	- Unpressed: power enabled
	- Use it when needed, but avoid unnecessary use just to stop the robot, as it damages the joints

# Robot boot

- Check the emergency stops
	- Green unpressed
	- Red unpressed
- Turn on the robot control cabinet using the on-off switch next to the power cable plug
	- The robot lights should turn white
- Turn on the computer (Cubi)
	- Log in
	- Open Firefox
	- Navigate to the robot web interface at address 172.16.0.2 (robot IP)
		- The first Firefox tab should navigate here by default
- Make sure the robot is free of obstacles, as it will slightly move during boot.
- In the web-interface, press the unlock button
	- All joints should unlock
	- When attached, the gripper should initialize by closing and opening
- The robot can now be guided using the two opposing buttons near the end-effector
	- One of those two buttons is a three-phase button, which must be pressed into the middle mode (not too soft and not too hard) to enable guiding.
- Pressing the green button disables the guiding mode and makes the robot accept control commands

# Enabling robot FCI

The Franka Control Interface (FCI) allows low-level commands over the LibFranka API.
The FCI  is also required to accept commands over ROS2.

- Ensure the green button is pressed
- In the robot web interface, click the "controller" icon at the top of the screen (with robot name and IP address near it) and press "Enable FCI".
	- The robot lights should turn green
	- It is possible to unpress the green button to go back to guiding mode. This will block FCI commands.

# Robot shutdown

**Always shut down the robot when you stop using it!**

- Ensure the robot is not moving (e.g. green button unpressed)
- In the robot web interface, press the lock symbol
	- The joints should lock
- Select  the "controller" icon at the top of the screen, then press "shut down"
	- The fans in the control cabinet should stop
	- Robot should show a white light
- Turn off the robot control cabinet using the on-off switch next to the power cable plug
- Turn off the computer (Cubi)
