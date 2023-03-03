# esp32-idf-lvgl
Sample ESP-IDF based project with integrated LVGL

This sample ilustrates the integration of the [lvgl](https://github.com/lvgl/lvgl) graphics library in a project based on the [espressif](https://docs.espressif.com/projects/esp-idf/en/release-v4.4/esp32/index.html) IoT development framework.

It uses the `develop` branch of the display drivers [repo](https://github.com/lvgl/lvgl_esp32_drivers/tree/develop) supportng various display controllers.

As this is still work-in-progres it was dificult to figure out how to properly initialize the display driver for the lvgl library.

To build the project you need to install the ESP-IDF framework:

```
git clone --recursive https://github.com/espressif/esp-idf.git
cd esp-idf; git checkout v4.4.3; git submodule update --init --recursive;
./install.sh
cd ..
```

Then each time a new terminal is opened the framework should be activated:
```
cd esp-idf; . ./export.sh; cd ..
```

There is a sample configuration file `sdkconfig.ttgo-t-display` for TTGO T-Display configured in landscape mode.

You can rename it to `sdkconfig` or configure the drivers library for another device using following command:
```
idf.py menuconfig
```

To build the project execute:
```
idf.py build
```

And to flash the device and monitor the output (press `ctrl-T` and then `ctrl-X` to exit) use:

```
idf.py flash monitor
```
