# STM32 timer frequency calculation

$$
\text{Timer频率} = \frac{\text{Timer2输入时钟}}{(\text{PSC} + 1) \times (\text{ARR} + 1)}
$$

Timer2的输入时钟是相应的APB1总线的时钟频率，因为Timer2一般挂在APB1上。
