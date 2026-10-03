# U20CAM-IMX662-S1:

## Hardware 

For hardware please refer to the user manual

## Software 

For software please refer to below link :

[UVC Camera Software](https://github.com/INNO-MAKER/UVC-Camera-Software)



## Known Issues

1. MJPG Frame Rate Drop with Low Light Compensation in Extremely Low-Light Conditions

   ##### Low Light Compensation in MJPG Mode

   When using the IMX662 USB camera with AMCap or other UVC-compatible software, enabling **Low Light Compensation** under extremely low-light conditions may cause the frame rate in **MJPG mode to gradually decrease**, accompanied by image quality degradation and a significant increase in image noise.

   This occurs because Low Light Compensation attempts to improve image visibility in dark environments by **reducing the frame rate to allow longer exposure times and increasing the sensor/ISP gain**. Under extremely low-light conditions, these adjustments may continue as the system attempts to obtain a brighter image.

   The current ISP implementation does not yet enforce a minimum frame-rate limit for this automatic adjustment. As a result, the MJPG frame rate may continue to decrease and, in some cases, may even become lower than the frame rate observed in YUV mode.

   ##### Current Recommendation

   For applications in extremely low-light environments, we currently recommend:

   - **Disable Low Light Compensation** and manually adjust the exposure and gain settings to achieve the best balance between brightness, noise, and frame rate.
   - Alternatively, use **YUV format** if more stable frame-rate behavior is required under low-light conditions.

   ##### Planned Improvement

   We are currently testing and optimizing the low-light control strategy. A future software/firmware update is planned to introduce a **minimum frame-rate limit** for automatic low-light adjustment, such as **20 FPS or 30 FPS**, to prevent excessive frame-rate reduction.

   The final frame-rate limit and related parameters are still under evaluation to achieve the best balance between **low-light image quality, noise level, exposure, and frame-rate stability**.

## FAQ





