โปรแกรมนี้จะเรียกใช้ function เปิดและปิด LED แทนการตั้งค่าให้เปิดและปิดใน app_main()

```css
#include <unistd.h>      	// header for usleep()
#include "driver/gpio.h"	// header for gpio
#include "LED.h"
const gpio_num_t LED1 = GPIO_NUM_23; 	//Define name 'GPIO_NUM_23' as 'LED1'

void LED_Init()
{
    gpio_set_direction(LED1, GPIO_MODE_OUTPUT);
}

void LED_On()
{
    gpio_set_level(LED1, 1);
}

void LED_Off()
{
    gpio_set_level(LED1, 0);
}

void app_main(void)
{
    LED_Init();
    while (true)
    {
        LED_On();
        usleep(500000);
        LED_Off();
        usleep(500000);
    }
}
```
Repo:https://github.com/Siracha192/LabSheet-03

Youtube:https://youtube.com/shorts/CnN3QUSVdlk?feature=share
