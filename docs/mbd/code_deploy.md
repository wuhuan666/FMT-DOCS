
## Deploy Your Model

It is very simple to deploy the code generated by the model into the FMT Firmware. Basically, you just need copy the generated file (*.c, *.h) to the location of the corresponding model and replace the old code. The following is the path to store the model code:

- **FMS**: `FMT-Firmware/src/model/fms/base_fms/lib`
- **INS**: `FMT-Firmware/src/model/ins/base_ins/lib`
- **Controller**: `FMT-Firmware/src/model/control/base_controller/lib`
- **Plant**: `FMT-Firmware/src/model/plant/multicopter/lib`

If there is no corresponding model directory created for your new model. Please follow the below steps to create one (take the controller as an example):

- Copy the directory of `FMT-Firmware/src/model/control/template_controller` and give it a new name, such as `FMT-Firmware/src/model/control/fw_controller`.
- Copy all generated code (*.c, *.h) to `FMT-Firmware/src/model/control/fw_controller/lib` directory.
- Modify `control_interface.c`. Add model interface code to establish the connection with other modules.

## Deploy Your C/C++ Code

If you have algorithm which is written by C/C++ and wants to integrate it into FMT Firmware, it is also possible. In general, the whole proecss is similiar as model deployment. Instead of copy the generated code you copy your C/C++ code to `FMT-Firmware/src/model/control/fw_controller/lib` folder and keep the *Controller.h* file.
