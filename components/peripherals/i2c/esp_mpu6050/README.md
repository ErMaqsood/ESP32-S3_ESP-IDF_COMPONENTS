# InvenSense MPU6050 Sensor

[![License: MIT](https://cdn.prod.website-files.com/5e0f1144930a8bc8aace526c/65dd9eb5aaca434fac4f1c34_License-MIT-blue.svg)](/LICENSE)
[![Edited with VS Code](https://badgen.net/badge/icon/VS%20Code?icon=visualstudio&label=edited%20with)](https://visualstudio.microsoft.com)
[![Build with PlatformIO](https://img.shields.io/badge/build%20with-PlatformIO-orange?logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB3aWR0aD0iMjUwMCIgaGVpZ2h0PSIyNTAwIiB2aWV3Qm94PSIwIDAgMjU2IDI1NiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiBwcmVzZXJ2ZUFzcGVjdFJhdGlvPSJ4TWlkWU1pZCI+PHBhdGggZD0iTTEyOCAwQzkzLjgxIDAgNjEuNjY2IDEzLjMxNCAzNy40OSAzNy40OSAxMy4zMTQgNjEuNjY2IDAgOTMuODEgMCAxMjhjMCAzNC4xOSAxMy4zMTQgNjYuMzM0IDM3LjQ5IDkwLjUxQzYxLjY2NiAyNDIuNjg2IDkzLjgxIDI1NiAxMjggMjU2YzM0LjE5IDAgNjYuMzM0LTEzLjMxNCA5MC41MS0zNy40OUMyNDIuNjg2IDE5NC4zMzQgMjU2IDE2Mi4xOSAyNTYgMTI4YzAtMzQuMTktMTMuMzE0LTY2LjMzNC0zNy40OS05MC41MUMxOTQuMzM0IDEzLjMxNCAxNjIuMTkgMCAxMjggMCIgZmlsbD0iI0ZGN0YwMCIvPjxwYXRoIGQ9Ik0yNDkuMzg2IDEyOGMwIDY3LjA0LTU0LjM0NyAxMjEuMzg2LTEyMS4zODYgMTIxLjM4NkM2MC45NiAyNDkuMzg2IDYuNjEzIDE5NS4wNCA2LjYxMyAxMjggNi42MTMgNjAuOTYgNjAuOTYgNi42MTQgMTI4IDYuNjE0YzY3LjA0IDAgMTIxLjM4NiA1NC4zNDYgMTIxLjM4NiAxMjEuMzg2IiBmaWxsPSIjRkZGIi8+PHBhdGggZD0iTTE2MC44NjkgNzQuMDYybDUuMTQ1LTE4LjUzN2M1LjI2NC0uNDcgOS4zOTItNC44ODYgOS4zOTItMTAuMjczIDAtNS43LTQuNjItMTAuMzItMTAuMzItMTAuMzJzLTEwLjMyIDQuNjItMTAuMzIgMTAuMzJjMCAzLjc1NSAyLjAxMyA3LjAzIDUuMDEgOC44MzdsLTUuMDUgMTguMTk1Yy0xNC40MzctMy42Ny0yNi42MjUtMy4zOS0yNi42MjUtMy4zOWwtMi4yNTggMS4wMXYxNDAuODcybDIuMjU4Ljc1M2MxMy42MTQgMCA3My4xNzctNDEuMTMzIDczLjMyMy04NS4yNyAwLTMxLjYyNC0yMS4wMjMtNDUuODI1LTQwLjU1NS01Mi4xOTd6TTE0Ni41MyAxNjQuOGMtMTEuNjE3LTE4LjU1Ny02LjcwNi02MS43NTEgMjMuNjQzLTY3LjkyNSA4LjMyLTEuMzMzIDE4LjUwOSA0LjEzNCAyMS41MSAxNi4yNzkgNy41ODIgMjUuNzY2LTM3LjAxNSA2MS44NDUtNDUuMTUzIDUxLjY0NnptMTguMjE2LTM5Ljc1MmE5LjM5OSA5LjM5OSAwIDAgMC05LjM5OSA5LjM5OSA5LjM5OSA5LjM5OSAwIDAgMCA5LjQgOS4zOTkgOS4zOTkgOS4zOTkgMCAwIDAgOS4zOTgtOS40IDkuMzk5IDkuMzk5IDAgMCAwLTkuMzk5LTkuMzk4em0yLjgxIDguNjcyYTIuMzc0IDIuMzc0IDAgMSAxIDAtNC43NDkgMi4zNzQgMi4zNzQgMCAwIDEgMCA0Ljc0OXoiIGZpbGw9IiNFNTcyMDAiLz48cGF0aCBkPSJNMTAxLjM3MSA3Mi43MDlsLTUuMDIzLTE4LjkwMWMyLjg3NC0xLjgzMiA0Ljc4Ni01LjA0IDQuNzg2LTguNzAxIDAtNS43LTQuNjItMTAuMzItMTAuMzItMTAuMzItNS42OTkgMC0xMC4zMTkgNC42Mi0xMC4zMTkgMTAuMzIgMCA1LjY4MiA0LjU5MiAxMC4yODkgMTAuMjY3IDEwLjMxN0w5NS44IDc0LjM3OGMtMTkuNjA5IDYuNTEtNDAuODg1IDIwLjc0Mi00MC44ODUgNTEuODguNDM2IDQ1LjAxIDU5LjU3MiA4NS4yNjcgNzMuMTg2IDg1LjI2N1Y2OC44OTJzLTEyLjI1Mi0uMDYyLTI2LjcyOSAzLjgxN3ptMTAuMzk1IDkyLjA5Yy04LjEzOCAxMC4yLTUyLjczNS0yNS44OC00NS4xNTQtNTEuNjQ1IDMuMDAyLTEyLjE0NSAxMy4xOS0xNy42MTIgMjEuNTExLTE2LjI4IDMwLjM1IDYuMTc1IDM1LjI2IDQ5LjM2OSAyMy42NDMgNjcuOTI2em0tMTguODItMzkuNDZhOS4zOTkgOS4zOTkgMCAwIDAtOS4zOTkgOS4zOTggOS4zOTkgOS4zOTkgMCAwIDAgOS40IDkuNCA5LjM5OSA5LjM5OSAwIDAgMCA5LjM5OC05LjQgOS4zOTkgOS4zOTkgMCAwIDAtOS4zOTktOS4zOTl6bS0yLjgxIDguNjcxYTIuMzc0IDIuMzc0IDAgMSAxIDAtNC43NDggMi4zNzQgMi4zNzQgMCAwIDEgMCA0Ljc0OHoiIGZpbGw9IiNGRjdGMDAiLz48L3N2Zz4=)](https://platformio.org/)
[![PlatformIO Registry](https://badges.registry.platformio.org/packages/k0i05/library/esp_mpu6050.svg)](https://registry.platformio.org/libraries/k0i05/esp_mpu6050)
[![ESP Component Registry](https://components.espressif.com/components/k0i05/esp_mpu6050/badge.svg)](https://components.espressif.com/components/k0i05/esp_mpu6050)

This ESP32 espressif IoT development framework (esp-idf) i2c peripheral driver was developed for the InvenSense MPU6050 6-axis motion tracking sensor.  Information on features and functionality are documented and can be found in the `mpu6050.h` header file and in the `documentation` folder.

## Repository

The component is hosted on github and is located here: <https://github.com/K0I05/ESP32-S3_ESP-IDF_COMPONENTS/tree/main/components/peripherals/i2c/esp_mpu6050>

## General Usage

To get started, simply copy the component to your project's `components` folder and reference the `mpu6050.h` header file as an include.  The component includes documentation for the peripheral such as the datasheet, application notes, and/or user manual where applicable.

```text
components
└── esp_mpu6050
    ├── CMakeLists.txt
    ├── README.md
    ├── LICENSE
    ├── idf_component.yml
    ├── library.json
    ├── documentation
    │   └── datasheets, etc.
    ├── include
    │   └── mpu6050_version.h
    │   └── mpu6050.h
    └── mpu6050.c
```

## Basic Example

Once a driver instance is instantiated the sensor is ready for usage as shown in the below example.   This basic implementation of the driver utilizes default configuration settings and makes a measurement request from the sensor at user defined interval and prints the results.

```c
#include <mpu6050.h>

void i2c0_mpu6050_task( void *pvParameters ) {
    // initialize the xLastWakeTime variable with the current time.
    TickType_t         last_wake_time   = xTaskGetTickCount ();
    //
    // initialize i2c device configuration
    mpu6050_config_t dev_cfg          = I2C_MPU6050_CONFIG_DEFAULT;
    mpu6050_handle_t dev_hdl;
    //
    // init device
    mpu6050_init(i2c0_bus_hdl, &dev_cfg, &dev_hdl);
    if (dev_hdl == NULL) {
        ESP_LOGE(APP_TAG, "mpu6050 handle init failed");
        assert(dev_hdl);
    }

    uint8_t                                 sample_rate_divider_reg;
    mpu6050_config_register_t               config_reg;
    mpu6050_gyro_config_register_t          gyro_config_reg;
    mpu6050_accel_config_register_t         accel_config_reg;
    mpu6050_interrupt_enable_register_t     irq_enable_reg;
    mpu6050_power_management1_register_t    power_management1_reg;
    mpu6050_power_management2_register_t    power_management2_reg;
    mpu6050_who_am_i_register_t             who_am_i_reg;

    /* attempt to read device sample rate divider register */
    mpu6050_get_sample_rate_divider_register(dev_hdl, &sample_rate_divider_reg);

    /* attempt to read device configuration register */
    mpu6050_get_config_register(dev_hdl, &config_reg);

    /* attempt to read device gyroscope configuration register */
    mpu6050_get_gyro_config_register(dev_hdl, &gyro_config_reg);

    /* attempt to read device accelerometer configuration register */
    mpu6050_get_accel_config_register(dev_hdl, &accel_config_reg);

    /* attempt to read device interrupt enable register */
    mpu6050_get_interrupt_enable_register(dev_hdl, &irq_enable_reg);

    /* attempt to read device power management 1 register */
    mpu6050_get_power_management1_register(dev_hdl, &power_management1_reg);

    /* attempt to read device power management 2 register */
    mpu6050_get_power_management2_register(dev_hdl, &power_management2_reg);

    /* attempt to read device who am i register */
    mpu6050_get_who_am_i_register(dev_hdl, &who_am_i_reg);

    // show registers
    ESP_LOGI(APP_TAG, "Sample Rate Divider Register:         0x%02x (%s)", sample_rate_divider_reg, uint8_to_binary(sample_rate_divider_reg));
    ESP_LOGI(APP_TAG, "Configuration Register:               0x%02x (%s)", config_reg.reg, uint8_to_binary(config_reg.reg));
    ESP_LOGI(APP_TAG, "Gyroscope Configuration Register:     0x%02x (%s)", gyro_config_reg.reg, uint8_to_binary(gyro_config_reg.reg));
    ESP_LOGI(APP_TAG, "Accelerometer Configuration Register: 0x%02x (%s)", accel_config_reg.reg, uint8_to_binary(accel_config_reg.reg));
    ESP_LOGI(APP_TAG, "Interrupt Enable Register:            0x%02x (%s)", irq_enable_reg.reg, uint8_to_binary(irq_enable_reg.reg));
    ESP_LOGI(APP_TAG, "Power Management 1 Register:          0x%02x (%s)", power_management1_reg.reg, uint8_to_binary(power_management1_reg.reg));
    ESP_LOGI(APP_TAG, "Power Management 2 Register:          0x%02x (%s)", power_management2_reg.reg, uint8_to_binary(power_management2_reg.reg));
    ESP_LOGI(APP_TAG, "Who am I Register:                    0x%02x (%s)", who_am_i_reg.reg, uint8_to_binary(who_am_i_reg.reg));
    //
    // task loop entry point
    for ( ;; ) {
        ESP_LOGI(APP_TAG, "######################## MPU6050 - START #########################");
        //
        // handle sensor
        float temperature;
        mpu6050_gyro_data_axes_t gyro_data;
        mpu6050_accel_data_axes_t accel_data;
        esp_err_t result = mpu6050_get_motion(dev_hdl, &gyro_data, &accel_data, &temperature);
        if(result != ESP_OK) {
            ESP_LOGE(APP_TAG, "mpu6050 device read failed (%s)", esp_err_to_name(result));
        } else {
            /* pitch and roll */
            float pitch = atanf(accel_data.x_axis / sqrtf(powf(accel_data.y_axis, 2.0f) + powf(accel_data.z_axis, 2.0f)));
            float roll  = atanf(accel_data.y_axis / sqrtf(powf(accel_data.x_axis, 2.0f) + powf(accel_data.z_axis, 2.0f)));

            ESP_LOGI(APP_TAG, "Accelerometer X-Axis: %fg", accel_data.x_axis);
            ESP_LOGI(APP_TAG, "Accelerometer Y-Axis: %fg", accel_data.y_axis);
            ESP_LOGI(APP_TAG, "Accelerometer Z-Axis: %fg", accel_data.z_axis);
            ESP_LOGI(APP_TAG, "Gyroscope X-Axis:     %f°/sec", gyro_data.x_axis);
            ESP_LOGI(APP_TAG, "Gyroscope Y-Axis:     %f°/sec", gyro_data.y_axis);
            ESP_LOGI(APP_TAG, "Gyroscope Z-Axis:     %f°/sec", gyro_data.z_axis);
            ESP_LOGI(APP_TAG, "Temperature:          %f°C", temperature);
            ESP_LOGI(APP_TAG, "Pitch Angle:          %f°", pitch);
            ESP_LOGI(APP_TAG, "Roll Angle:           %f°", roll);
        }
        //
        ESP_LOGI(APP_TAG, "######################## MPU6050 - END ###########################");
        //
        //
        // pause the task per defined wait period
        //vTaskDelaySecUntil( &last_wake_time, I2C0_TASK_SAMPLING_RATE / 2 );
        vTaskDelaySecUntil( &last_wake_time, 1 );
    }
    //
    // free resources
    mpu6050_delete( dev_hdl );
    vTaskDelete( NULL );
}
```

Copyright (c) 2024 Eric Gionet (<gionet.c.eric@gmail.com>)
