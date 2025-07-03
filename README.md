 🚀 STM32 Bare-Metal GPIO + EXTI Interrupt Example

This project demonstrates bare-metal programming on the STM32 Nucleo-F401RE using CMSIS registers only (no HAL/LL), focusing on:

- Blinking an LED (PA5) using the main loop
- Toggling another LED (PA6) using an external interrupt from a push button on PC13

🛠️ Hardware Used

- STM32 Nucleo-F401RE
- Onboard blue push button (connected to PC13)
- Onboard green LED (connected to PA5)
- Additional LED (connected to PA6) – optional for external LED toggle

🔧 How It Works

Main Loop (PA5)
- PA5 is configured as an output
- Inside main()PA5 toggles continuously to simulate a background task

Interrupt (PC13 → PA6)
- PC13 is configured as an input (button)
- External interrupt on falling edge (EXTI13) is set up
- When the button is pressed:
  - ISR (EXTI15_10_IRQHandler) is triggered
  - Inside ISR, PA6 toggles (interrupt-driven action)

🔑 Key Concepts Implemented

- ✅ GPIO Initialization using MODER and ODR
- ✅ External Interrupt Configuration using SYSCFG->EXTICR
- ✅ Interrupt Masking and Edge Trigger with EXTI->IMR and EXTI->FTSR
- ✅ NVIC Interrupt Enabling for EXTI15_10_IRQn
- ✅ Interrupt Service Routine (ISR)* implementation
- ✅ Software delay loop using __NOP() for visible LED blinking
