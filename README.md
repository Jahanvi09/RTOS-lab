# RTOS-lab
This is a program for creating two different tasks (1. Serial Printing and 2. Temperature and Humidity reading with DHT11) and control the tasks using different functions in FreeRTOS library.
Requirements:

Arduino IDE
FreeRTOS Library included in Arduino IDE
Arduino Board (Arduino UNO, Nano, Mega..etc)
Note: I'm using Arduino Mega connected to COM6 (The Port can be viewed in device manager under ports section)


Functions we use:


vTaskDelay () - vTaskDelay() specifies a time at which the task wishes to unblock relative to the time at which vTaskDelay() is called. For example, specifying a block period of 100 ticks will cause the task to unblock 100 ticks after vTaskDelay() is called. vTaskDelay() does not therefore provide a good method of controlling the frequency of a periodic task as the path taken through the code, as well as other task and interrupt activity, will effect the frequency at which vTaskDelay() gets called and therefore the time at which the task next executes. See vTaskDelayUntil() for an alternative API function designed to facilitate fixed frequency execution. It does this by specifying an absolute time (rather than a relative time) at which the calling task should unblock.
uxTaskPriorityGet () - vTaskDelay() obtains the priority of the task.
vTaskPrioritySet () - vTaskPrioritySet () sets the priority of any task. A context switch will occur before the function returns if the priority being set is higher than the currently executing task.
vTaskSuspend () - vTaskSuspend () suspends any task. When suspended a task will never get any microcontroller processing time, no matter what its priority. Calls to vTaskSuspend are not accumulative – i.e. calling vTaskSuspend () twice on the same task still only requires one call to vTaskResume () to ready the suspended task.
vTaskResume () - vTaskResume () resumes a suspended task. A task that has been suspended by one or more calls to vTaskSuspend () will be made available for running again by a single call to vTaskResume ().
Procedure:

Connect the circuit .
Upload the code inside the folder CODE by connecting your Arduino and selecting the board
Open your serial monitor and run the following commands to see the outputs.
Case ‘s’ - Suspends the task of blinking the led with delay (using vTaskDelay())
Case ‘r’ - Resumes the task of blinking the led with delay (using vTaskDelay())
Note: Both s and r cases prints their priority using uxTaskPriorityGet()
Case ‘a’ & ‘b’ – Interchanges the priority of the tasks using vTaskPrioritySet()
You will see the following outputs in your serial monitors


Conclusion:
We successfully learned to control two different tasks using the task control functions. We also changed the priority of the tasks.
